# C++ 코딩 표준
----
## -. 기본 원칙

### 1. 가독성을 최우선으로 삼는다. (대부분의 경우 코드는 그 자체가 문서의 역할을 해야 함)
### 2. 문제가 있을 경우 최대한 빨리 크래시가 나거나 assert에 걸리도록 코드를 작성한다. 어떻게든 프로그램을 돌게 만들다가 나중에 크래시가 나는 것보다 나쁜 상황은 없다.
### 3. 정말 합당한 이유가 있지 않는 한, 통합개발환경(IDE)의 자동 서식을 따른다. (비주얼 스튜디오의 "Ctrl + K + D" 기능)
### 4. 본 코딩표준을 따라 잘 짜여진 기존의 코드에서 배운다.
----
## -. 메인 코딩 표준

### 1. 클래스와 구조체의 이름은 파스칼 표기법을 따른다.
#### 클래스에는 C를 붙인다.
```cpp
class CPlayerManager;
struct AnimationInfo;
```
#### * 파르칼 표기법 : 모든 단어에서 첫 글자를 대문자로 쓰는 방식

### 2. 지역 변수 그리고 함수의 매개 변수의 이름은 파르칼 표기법을 따르며 앞에 자료형을 표기한다.
```cpp
void SomeMethod(const int nSomeParameter)
{
  int nSomeNumber;
  struct stPlayer;
}
```

### 3. 메서드 이름은 동사-목적어 쌍으로 표기하며 파스칼 표기법을 따른다.
```cpp
void DoSomething();
```

### 4. 상수 또는 #define으로 정의된 상수의 이름은 모두 대문자로 하되 밑줄로 각 단어를 분리한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/38895e0d-cc0d-4294-9f1c-74ff67a2ea90)
#### Constexpr : <https://blockdmask.tistory.com/482>

### 5. 네임스페이스는 모두 소문자로 작성한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/eef89755-d6fd-4001-adee-a13aef96f75b)

### 6. boolean형 변수는 앞에 b를 붙인다.
```cpp
bool m_bfriend;
```

### 7. 인터페이스를 선언할 때는 앞에 I를 붙인다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/2ba11176-6ec7-4f30-9255-03c045ca6f64)

### 8. 열거형을 선언할 때는 앞에 e를 붙인다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/7a436af9-af75-4d8f-85dd-593d2da6ecd9)

### 9. 클래스 멤버 변수명은 앞에 m_을 붙인다.

```cpp
bool m_bfriend;
int m_nAge;
```

### 10. goto문 사용은 최대한 지양하되, goto 사용시에 레이블 명은 모두 대문자로 하되 밑줄로 각 단어를 분리한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/ba3918b1-7db2-4ba3-b863-ad7e110589a6)

### 11. 값을 반환하는 함수의 이름은 무엇을 반환하는지 알 수 있게 짓는다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/ff93358c-bf69-4b1d-ac4c-c0fb3f658f5b)

### 12. 단순히 반복문에 사용되는 변수가 아닌 경우에는 i, e 같은 변수명 대신 index, employee 처럼 변수에 저장되는 데이터를 한눈에 알아볼 수 있는 변수명을 사용한다.

### 13. 줄임말도 카멜 표기법을 사용한다.
```cpp
int m_nOrderId;
```

### 14. 클래스 멤버 변수에 접근 할 때는 항상 setter와 getter를 사용한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/07471452-067f-468c-b4f2-d266608aa928)

### 15. 구조체는 public 멤버 변수와 생성자만 가질 수 있다. 구조체의 멤버 변수명은 파스칼 표기법을 따르며, 구조체 안에서 함수는 사용하지 않는다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/d992bce0-6c78-4380-a078-7f244206396b)

### 16. 외부 헤더 파일을 인클루드 할 때는 #include<> 을 사용. 자체적으로 만든 헤더 파일을 인클루드 할 때는 #include "" 를 사용한다.

### 17. 외부 헤더 파일을 먼저 인클루드한 뒤, 내부 헤더 파일을 인클루드 한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/0b2c5421-334b-4c22-a4ed-70a1fed3bb0a)

### 18. 모든 헤더 파일 첫 번째 줄에 #pragma once를 기재한다.

### 19. double이 반드시 필요한 경우가 아닌 이상 부동 소수점 값에 f를 붙여준다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/fb9fbb20-973e-44f4-aa51-1643a78829ac)

### 20. switch case 문에는 항상 default:를 넣는다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/13dab2ed-1e79-43fe-8004-62b48c6a18fc)

### 24. switch case 문 끝에 break;를 넣지 않고 그 바로 아래 case 문의 코드를 실행하고 싶은 경우, 미리 정의해둔 FALLTHROUGH 매크로를 추가한다. 단, case 문 안에 코드가 없는 경우는 예외이다. 이는 C++17 사양에서 [[fallthrough]] 애트리뷰트로 대체될 것이다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/eaece446-d8b1-4dc8-86df-c282937b012c)
#### *Fall-Through : 일반적으로 switch 문에서 case 블록의 끝에 break; 문이 없으면, 다음 case 블록으로 "fall-through"됩니다. 이는 의도치 않은 동작을 초래할 수 있으므로, 개발자가 의도적으로 "fall-through"를 사용할 때 주석이나 FALLTHROUGH 매크로를 추가하는 것이 좋다.
#### 예시 (C++17 미만 버전)
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/ae731380-9d3f-4368-96d6-c19cddff6c59)
#### 또는 
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/eec84222-cfd4-4735-8027-92fdf19dd6b6)
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/1b8b80fd-24bd-4f26-9819-2704dd6181dd)
#### 예시 (C++17 이상 버전)
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/4647a56f-3b9a-4180-bf12-9752387a6688)
#### 또는
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/0a806f95-afd8-4bf1-80b6-7c7513db2099)

### 22. default case가 절대 실행될 일이 없는 경우, default case 안에 Assert(false); 란 코드를 추가한다. Assert()를 직접 구현하면 그 안에서 릴리즈 빌드 시 최적화 힌트를 추가할 수 있다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/2ff5bc8d-defa-4fd5-bb96-2db5763f20d5)
#### *Assert : C 및 C++ 프로그래밍에서 디버깅 목적으로 사용되는 매크로 (조건이 false일 때 assertion failure 발생)

### 23. 가능한 최대한 const를 사용한다. 여기에는 지역 변수와 함수 매개 변수도 포함된다.

### 24. 개체를 수정하지 않는 멤버 함수에는 모두 const를 붙인다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/75e0d0b3-9e39-49ae-8e06-e6a3e63873aa)

### 25. 값(value) 형식의 변수를 const로 반환하지 않는다. 포인터나 참조(reference)를 반환할 경우에만 const 반환을 한다.

### 26. 재귀 함수는 이름 뒤에 Recursive를 붙인다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/af88674b-7e89-439c-be87-87e93dda5541)

### 27. 클래스 안에서 멤버 변수와 메서드의 등장 순서는 다음을 따른다.
#### 1) public 메서드들
#### 2) public 변수들
#### 3) protected 메서드들
#### 4) protected 변수들
#### 5) private 메서드들
#### 6) private 변수들

### 28. 대부분의 경우 함수 오버로딩을 피한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/e2fb7aab-30f1-419b-a00d-7197ba61a639)

### 29. const 반환을 위한 함수 오버로딩은 허용한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/6b20fcd5-1f64-4b20-8d93-b0bed548c84b)

### 30. const_cast를 직접적으로 사용하지 않는다. 대신 const인 개체를 수정 가능한 형태로 변환해서 반환하는 함수를 만든다.
#### *const_cast : const로 선언된 포인터를 일반 포인터로 캐스팅해주는 역할 (포인터가 아닌 일반 변수나 함수 포인터, 멤버 함수에는 사용 불가)
#### ex)
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/185dd5c3-3af9-4590-a949-7c9cc2db6f1b)
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/a970990e-7084-402e-9251-6c60961e430d)

### 31. 클래스는 각각 독립된 소스 파일에 있어야 한다. 단, 작은 클래스 몇 개를 한 파일 안에 같이 넣어두는 것이 상식적일 경우 예외를 허용한다.

### 32. 파일 이름은 대소문자까지 포함해서 반드시 클래스 이름과 일치해야 한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/9f289eee-b01f-4670-914e-f18682d5c3dd)

### 33. 여러 파일이 하나의 클래스를 이룰 때, 파일 이름은 클래스 이름으로 시작하고, 그 뒤에 밑줄과 세부 항목 이름을 붙인다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/20b3638c-6e09-49fb-a4df-679736ba954b)

### 34. Reverse OOP 패턴을 사용할 때, 플랫폼 전용 클래스는 위 항목과 비슷한 명명 규칙을 사용한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/b0dbcc13-a700-4ba4-b82f-53898c6e92b0)
#### <https://cafemocamoca.tistory.com/199>

### 35. 표준 C assert 대신에 자신만의 Assert 버전을 구현한다.

### 36. 특정 조건이 반드시 충족되어야 한다고 가정(assertion)하고 짠 코드 모든 곳에 assert를 사용한다. Assert는 복구 불가능한 조건이다. Assert는 릴리즈 빌드에서 __assume 키워드로 대체하여 컴파일러에 최적화 힌트를 줄 수 있다.

### 37. 모든 메모리 할당은 직접 구현한 New, Delete 키워드를 통해 호출한다.

### 38. memset, memcpy, memmove와 같은 메모리 연산 역시 우리 고유의 MemSet, MemCpy, MemMove 키워드를 통해 호출해야 한다.
#### *Why : std::memcpy, std::memmove, std::memset, std::memcmp, 대신해 std::copy, std::move, std::fill, and std::equal[1] 를 사용하자.타입안정적이며 성능도 더 느리지 않으며 더 나아질 여지도 있다.
출처: https://hamait.tistory.com/1043

### 39. 어떤 이유로든 매개변수로 nullptr가 넘어올 수 있는 경우가 아니라면, 포인터 대신 참조자( & )를 사용하는 것을 원칙으로 한다. (예외는 다음 항목을 참고)

### 40. 함수에서 매개변수를 통해 값을 반환할 때(out 매개변수)는 포인터를 사용하며, 매개변수 이름 앞에 out을 붙인다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/ebe55648-0cda-4e7f-9510-0ebbf22321f2)

### 41. 위 항목의 out 매개 변수는 반드시 null이 아니어야 한다. (함수 내부에서 if 문 대신 assert를 사용할 것)
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/99641ec8-ea57-4826-8f74-c846c72da877)

### 42. 매개 변수가 클래스 내부에서 저장될 때는 포인터를 사용한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/a8384503-d40c-446e-9be7-dda0cf9305f3)

### 43. 매개 변수가 void 포인터여야 하는 경우는 포인터를 사용한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/05b23c37-7e43-403f-ba32-0cc10e73dd30)

### 44. 비트 플래그 열거형은 이름 뒤에 Flags를 붙인다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/75fd7dcc-a478-4b84-acdc-87965b8a147f)

### 45. 특정 크기(예를 들어, 데이터 멤버의 직렬화를 위한 크기)가 필요하지 않은 한 열거형에 크기 지정자를 추가하지 않는다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/1bbbc966-07f4-4bba-b1c4-9462eb2c8590)

### 46. 디폴트 매개 변수 대신 함수 오버로딩을 선호한다.

### 47. 디폴트 매개 변수를 사용하는 경우, nullptr 나 false, 0 같이 비트 패턴이 0인 값을 사용한다.

### 48. 가능한 한 고정된 크기(size)의 컨테이너를 사용한다.

### 49. 동적 컨테이너를 사용해야 한다면 가능한 한 미리 reserve()를 호출한다.

### 50. #define 으로 정의된 상수는 항상 괄호로 감싸준다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/6236d198-59b7-4488-8eb2-35b0fda3da4d)
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/35a7fd6c-f2b5-4cca-9313-7159136e7e1b)

### 51. 상수는 #define 보다 const 상수 변수로 선언한다.

### 52. 클래스를 상호 참조할 때는 #include 보다 전방선언(forward declaration)을 최대한 이용한다.
#### * 클래스 전방선언 : 헤더파일에서 헤더파일을 포함시키는 행위가 컴파일 시간을 증가시키기 때문에 이를 막기 위해 포인터 객체를 선언할 때에는 클래스 선언 전에 필요한 클래스를 명시하여 헤더파일의 중복을 막을 수 있다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/d83da586-64be-4856-b60c-d52c3f5ce5c3)

### 53. 모든 컴파일러 경고는 최대한 고친다.

### 54. 변수 가리기(variable shadowing)는 허용되지 않는다. 외부 변수가 동일한 이름을 사용중이라면 내부 변수에는 다른 이름을 사용한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/e6bc76bf-d9f5-42f2-a01c-04a6443d61ec)

### 55. 한 줄에 변수 하나만 선언한다.
#### 가독성 향상
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/3a7abe30-5b9a-4578-96c8-79fceeaede71)

### 56. 지역 객체를 반환할 때 NRVO의 이점을 활용한다. 이는 함수 내에 하나의 return문 만 쓴다는 것을 의미하며, 이것은 값으로 객체를 반환할 때만 적용된다.
#### <https://m.post.naver.com/viewer/postView.naver?volumeNo=9735713&memberNo=559061> 
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/884103e7-f545-4665-a090-92f214e30ccf)
#### NRVO, RVO의 차이
#### NRVO 예시
```cpp
MyClass func()
{
  MyClass obj;
  //작업
  // obj를 봔환
  return obj;
}
```
#### RVO 예시
```cpp
MyClass func()
{
  //작업
  // 직접 반환
  return MyClass(0);
}
```

### 57. 멤버 변수를 초기화할 때는 초기화 리스트를 사용하는 것을 기본으로 한다.

----
## -. 소스 코드 포맷팅
### 1. include 전처리문 블록과 코드 본문 사이에 반드시 빈 줄이 있어야 한다.

### 2. 탭(tab)은 비주얼 스튜디오 기본값을 사용하며, 비주얼 스튜디오를 사용하지 않을 시 띄어쓰기 4칸을 탭으로 사용한다.

### 3. 중괄호( { )를 열 때는 언제나 새로운 줄에 연다.

### 4. 중괄호 안( { } )에 코드가 한 줄만 있더라도 반드시 중괄호를 사용한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/2b33fb02-24be-4a7c-876f-aeab15b3012c)

### 5. 포인터나 참조 기호는 자료형에 붙인다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/de6fe8c7-a6e2-48de-90cc-e22a87c43ee7)

### 6. 초기화 리스트를 이용해 멤버 변수를 초기화할 때는 아래와 같은 포맷을 따라 한 줄에 변수 하나씩 초기화한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/e60ff0eb-b0fb-4f62-98cc-ed664c4ae44d)

----
## -. 소스 코드 포맷팅
### 1. override 와 final 키워드를 최대한 사용한다.
#### * final : 클래스를 더이상 상속 불가능한 클래스로 만드는 역할
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/6dcf6acc-5410-4d31-993f-48cbaffc3b21)
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/97c1d7f6-f530-4aef-be3e-c57605b041eb)

### 2. 항상 enum class 를 사용한다.
####  ![image](https://github.com/ParkGY94/NEPro/assets/59813824/d15b84e4-5bc7-4f21-92a5-13d16f92480d)
#### - enum class 장점
####   1) 멤버 변수의 이름이 중복 될 수 있다.
####   2) 서로 다른 enum class 타입끼리 비교할 수 없다.
####   3) 멤버 변수의 타입을 정할 수 있다.

### 3. 가능한 Assert 대신 static_assert 를 사용한다.
#### <https://reoul.github.io/cpp/cpp-37/>

### 4. 포인터에 NULL 대신 nullptr 를 사용합니다.
#### NULL은 포인터가 아니라 매크로에서 정의된 상수 0 이다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/624460ac-bcae-428c-ab62-5577721aa9b5)

### 5. 개체의 수명이 클래스 내에서만 처리되는 경우 unique_ptr 를 사용한다. (즉, 개체 생성은 생성자에서, 개체 파괴는 소멸자에서)

### 6. 적용 가능한 곳이라면 범위기반 for 문을 사용한다.
#### 범위기반 for문이란 기존의 for 반복문과 달리, 시작과 끝점을 알려주지 않아도 알아서 처음부터 끝까지 순회를 해주는 반복문 입니다
출처: https://blockdmask.tistory.com/319 [개발자 지망생:티스토리]
#### ex)
```
for(int elem : arr)
{
  cout << elem << endl;
}
```

### 7. 반복자나 new 키워드가 같은 줄에 있어서, 어떤 개체가 만들어지는 지 명확하게 드러나는 경우가 아니라면 auto 키워드를 사용하지 않는다.

### 8. std::move를 사용하여 수동으로 반환 값을 최적화하지 않는다. 이럴 경우, 자동 NRVO 최적화가 적용되지 않는다.

### 9. 이동 생성자(move constructor)와 이동 대입 연산자(move assignment operator)를 사용해도 된다.
#### <https://colinch4.github.io/2020-01-01/16_%EC%9D%B4%EB%8F%99-%EC%83%9D%EC%84%B1%EC%9E%90-%EB%B0%8F-%EC%9D%B4%EB%8F%99-%EB%8C%80%EC%9E%85-%EC%97%B0%EC%82%B0%EC%9E%90/>

### 10. 단순 상수 변수에는 const 대신 constexpr 을 사용한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/c4a90b17-f732-49d9-88e3-5b7bc26d9a4d)
