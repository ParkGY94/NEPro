# C++ Study 정리
----
## 1. 가상 함수 테이블

### C++은 가상 합수를 처리하기 위해, 가상 함수를 갖는 클래스 마다 가상 함수 테이블(virtual function table) 즉, 가상 함수 포인터를 모아둔 배열을 생성합니다. 이것의 이름을 vtable이라고 합니다.
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
### [ 기호 테이블 ( Symbol-Table ) 이란 ?
### c, c++ 컴파일 과정에서 .obj, .o 형식의 오브젝트 파일이 생성된다.
### 이 파일 안에 심볼 테이블이라는 데이터 구조가 존재하게 되는데, 이것을 통해 obj 파일의 여러 항목을 링커가 이해할 수 있는 이름으로 매핑시킨다.
### 그 밖에도 Variable name, Function name Objects, Classes, Interfaces 가 포함되며 보통 Hash Table 형태로 구현 된다. ] -----
### 또한 #define의 경우에는 사용한 횟수만큼 사본이 생성되지만, const 의 경우에는 사본이 단 한 번만 생성된다.

