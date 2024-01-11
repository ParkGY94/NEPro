# C++ Study 정리
----
## 1. 가상 함수 테이블

### C++은 가상 함수를 갖는 클래스 마다 가상 함수 테이블(virtual function table) 즉, 가상 함수 포인터를 모아둔 배열을 생성합니다. 이것의 이름을 vtable이라고 합니다.
### 또한 컴파일러는 가상 함수를 갖는 클래스 안에, 가상 함수 테이블을 가리키는 포인터를 멤버 변수로 몰래 추가시키는데 이를 vptr이라고 합니다.
### <https://nomad-programmer.tistory.com/359>
#### A 객체의 Func1 호출! -> A 클래스의 가상 함수 테이블의 주소 참조! -> 0x1024번지 참조!
### 파생클래스는 상위 클래스의 vtable을 그대로 받고 재정의 한 가상함수를 토대로 자신의 vtable을 수정, 갱신해 나갑니다. 
```cpp
class A
{
  public: 
    virtual void Draw() {cout << "A" << endl;}
};

class B: public A
{
  public:
    virtual void Draw() {cout << "B" << endl;}
};

void main()
{
  B b;
  A& a = b;
  a.Draw();
}
```
### 따라서 B b;로 객체를 생성하면 이 b 객체는 B클래스의 vtable을 가리키는 vptr을 가지므로 b 객체를 A클래스로 업캐스팅을 한 후 Draw()함수를 호출하면 B 클래스의 가상 함수 테이블을 따라가게 되므로, B::Draw()가 호출됩니다.

## 2. #define과 const 차이
### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/3fb19dc3-9393-4094-bf76-952c5f803b14)
### * 기호 테이블 ( Symbol-Table ) 이란 ?
### c, c++ 컴파일 과정에서 .obj, .o 형식의 오브젝트 파일이 생성된다.
### 이 파일 안에 심볼 테이블이라는 데이터 구조가 존재하게 되는데, 이것을 통해 obj 파일의 여러 항목을 링커가 이해할 수 있는 이름으로 매핑시킨다.
### 그 밖에도 Variable name, Function name Objects, Classes, Interfaces 가 포함되며 보통 Hash Table 형태로 구현 된다. 
### 또한 #define의 경우에는 사용한 횟수만큼 사본이 생성되지만, const 의 경우에는 사본이 단 한 번만 생성된다.

## 3. push_back과 emplace_back의 차이
### push_back은 객체를 삽입하기 위해서 똑같은 임시 객체를 하나 더 만들어서 거기에 복사한 다음 벡터에 삽입 -> 삽입이 끝나면 임시 객체 파괴 -> 잠깐 쓰고 버릴 메모리를 굳이 할당해 줘야 함. 임시 객체 생성자를 호출해서 생성하고 소멸자를 불러서 파괴시키는 과정에서 불필요한 연산이 생긴다.
### emplace_back은 가변인자 템플릿을 사용해서 삽입하려는 자료형에 따라 함수 내에서 삽입을 위한 객체를 자체 생성할 수 있다 -> 즉 똑같은 임시 객체를 만들 필요가 없다 -> 파괴해야 할 임시 객체 자체가 생기지 않는다 -> 잠깐 쓰고 버릴 메모리를 할당할 필요가 없다.
출처: https://hgu-can.tistory.com/entry/C-stdvector-pushback-vs-emplaceback-차이점 [코딩 공부하는 코딩류:티스토리]
### <https://growup-dev.tistory.com/entry/CC-vector-%ED%95%A8%EC%88%98pushback-emplaceback>

## 4. Initializer List를 사용해야 하는 이유
### Initializer List를 사용하여 초기화 하는 경우, 변수를 입력 값으로 바로 생성하지만
### Initailizer List를 사용하지 않고 중괄호를 사용할 경우, 변수를 생성 후 값을 입력하는 구조
### 따라서 Initailizer List가 효율적이며 Const 변수의 경우는 Initailizer List를 통해서만 초기화 할 수 있다.

## 5. RAII
### RAII는 Resource acquisition is initialization의 약자로 획득한 자원은 초기화 한다 라고 해석이 된다.
### 리소스 소유 스택 개체가 범위를 벗어나면 소멸자가 자동으로 호출되는 패턴
### ex) 스마트 포인터, lock_guard 등이 있다.

## 6. 객체 생성 규칙 Rule Of Five
### C++11 이전에는 Rule of Three C++11 이후에는 Rule of Five 규칙을 지킨다.
### Rule Of Five : 클래스 설계 시 소멸자, 복사 생성자, 복사 연산자, 이동 생성자, 이동 연산자 다섯 중 하나라도 사용자가 집접 구현한다면 나머지 넷도 모두 구현해야한다.
### Rule Of Three : 클래스 설계 시 소멸자, 복사 생성자, 복사 연산자 셋 중 하나라도 사용자가 집접 구현한다면 나머지 둘도 모두 구현해야한다.
### <https://object-world.tistory.com/6>

## 7. 디자인 패턴
### 디자인 패턴은 많은 개발자들이 직면하는 문제를 해결하기 위한 방법을 모아 체계적으로 일반화한 것이다. 일부 상속이 아닌 구조도 있지만 핵심은 "문제 해결을 위해 다형성을 이용하고 객체간에 어떤 관계를 만들 것인가"이다. 따라서 클래스 상속 방법과 이로 인해 만들어 지는 관계를 알고 있다면 어렵지 않게 학습하고 활용할 수 있다.
### 
