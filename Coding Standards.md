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
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/4ce33e31-1f4a-41c3-bd7c-167e026e4020)
#### * 파르칼 표기법 : 모든 단어에서 첫 글자를 대문자로 쓰는 방식

### 2. 지역 변수 그리고 함수의 매개 변수의 이름은 카멜 표기법을 따른다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/70ab0e46-17fd-4810-a385-3d41b38b6ba1)
#### * 카멜 표기법 : 첫 단어를 제외하고 나머지 단어의 첫 번째 글자만 대문자로 쓰는 방식

### 3. 메서드 이름은 동사-목적어 쌍으로 표기한다.
#### a. public 메서드의 이름은 파스칼 표기법을 따른다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/344012f1-81b9-462b-aee0-99fb28426fb2)
#### b. 그 외 다른 메서드의 이름은 카멜 표기법을 따른다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/253cf4f9-afdd-4492-ba95-526e772a1adb)

### 4. 상수 또는 #define으로 정의된 상수의 이름은 모두 대문자로 하되 밑줄로 각 단어를 분리한다.
#### ![image](https://github.com/ParkGY94/NEPro/assets/59813824/38895e0d-cc0d-4294-9f1c-74ff67a2ea90)
