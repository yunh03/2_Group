# 5주차

## **4주차 수업에서 나눈 질문들**

**다중 if문 사용 유무의 차이**

    A. 다중 if문을 사용하는 것과 사용하지 않는 것의 차이는 무엇일까?

    B. 시간 복잡도가 다르지 않을까?

    A. 프로그램의 효율성이 증대되고 가독성이 좋을 것 같아.

    B. 또한 다중 if문을 사용하지 않은 경우엔, 조건이 늘어날 수록 코드의 반복이 늘어날 것 같아.

    A. 확실히 다중if문을 사용하면 조건이 해당하는 경우에만 값을 출력하니까 반복된 패턴을 피할 수 있겠네.

    B. 이렇게 코드의 중복을 제거하고 수정에 용이하도록 내부 구조를 바꾸는 것을 '리팩토링'이라고 한대. 좋은 가독성과 높은 유지 보수성을 유지하면 서로 협업하기에 수월할 것 같아.

**switch, if, else if문의 차이**

    A. if문은 상위 하달식으로 조건문이 단계를 거쳐 실행되는 반면에 switch는 일치하는 상숫값을 바로 찾기 때문에 속도가 더 빠를 것 같아.

    B. 맞아. 그리고 switch문에서는 각 case마다 break를 사용해서 연쇄적인 조건을 실행시킬 수도 있어 유용한 것 같아. 하지만 반드시 사용해야 하기 때문에 신경 써야 하는 부분이도 해.

    A. if는 비교 연산이 수월하고 다양한 형태로 조건식을 구성할 수 있지만 switch는 상수를 이용해야 하기 때문에 비교 연산 등의 구현에 한계가 있어.

    B. 비교 연산을 할 때 조건이 많은 경우에는 if만을 사용하기보다 else if 함께 쓰면 가독성을 높일 수 있다고 하네.

    A. 찾아보니 if문은 branch statement 기반으로 조건을 만족하는지 안 하는지를 계속해서 확인해야 하고, switch문은 jump statement에 기반을 두고 있어서 실행해야 하는 코드로 빠르고 쉽게 넘어갈 수 있는 거라고 해. 

    B. 그렇구나.  switch는 나누기의 몫만 처리한다는 또 다른 특징이 있는데, 이 점을 잘 알고 사용해야겠다.

**예제 5-5**

    A. 먼저 printf를 이용해서 설명들을 출력해야겠다.

    B. scanf로 입력을 받고 input에 정수형 변수를 저장하여 출력할 거니까 scanf(”%d”, &input);을 선언한 뒤에, switch문은 어떻게 할까?

    A. 아침, 점심, 저녁 인사로 상숫값을 3개 지정하면 될 것 같아. 입력값이 1인 case 1에서는 “Good morning!!”을 출력하고, 입력값이 2인 case2에서는 “Good Afternoon!!”을 출력하는 식으로.

    B. case들이 연달아 실행되면 안 되니까 각각의 마지막 행에 break;를 적어줘야겠다.

    A. 각 상숫값마다 적어놓은 break를 지워서 실행해 보니 모든 문장이 출력되네. 

**예제 5-7, switch문-학점 계산**

    A. 먼저 0≤점수≤100에 해당하지 않으면 EXIT하는 조건은 switch문에서 어떻게 설정하지?

    B. if를 써도 되지 않을까? 

    A. 그러면 if문으로 예외를 먼저 설정하고, 나머지 점수들은 나누기의 몫으로 할당해서 상숫값을 선언하면 되겠다.

    B. 60 미만의 점수는 F학점으로 처리해야 해.

    A. case6 이외에 5부터 1까지의 경우를 새로 만들어도 되고, 아니면 default 값으로 처리할 수 있어.

    B. default 값으로 나머지 조건들을 처리해서 코드를 간결하게 해보자.

**교재 p168 08번 - 통신사 서비스 프로그램 구현**

    A. 먼저 age를 int로 정의해 준 뒤 나이 입력을 받기 위한 print문을 쓰자. 그리고 scanf로 age에 정수 입력을 받으면 될 것 같아.

    B. switch문을 이용해야 하니 입력받은 age를 10으로 나눠서 상숫값을 나누자. 40대는 case4, 20-30대는 혜택이 똑같으니 case3과 case2를 조건으로 달고 같은 값을 출력시키면 될 것 같아.

    A. 그러면 50대 이상과 이외의 연령대만 처리하면 되네. 0~10대를 case1과 case0과 같이 상숫값으로 처리하고 50대 이상을 default로 하면 어떨까?

    B. 50대 이상을 일일이 처리하지 않아도 돼서 좋은 생각인 것 같아. 

    A. 실행해보면 예외 처리도 잘 되고 각 연령대에 맞는 서비스가 알맞게 실행되네.
    
---

## **2주차 수업 내용 정리**

### 제어문

- 프로그램의 실행을 인위적으로 조절하여 이동 및 반복

    ex) 홀수는 출력, 짝수는 출력X

### 제어문의 종류

1. 선택문
    - if
        - 조건에 따른 명령 수행 지시 시 사용하는 명령문
        - true조건이 나올 때까지 반복
        - 조건식 부속 문장이 2개 이상일 경우 괄호 반드시 포함
          ![week5_1](https://github.com/yunh03/2_Group/blob/main/notes/src/week5_1.png)
    - if~else
        - 조건식이 참이면 if문, 거짓이면 else문 수행
        - 참이 아니면 아래 문장 모두 수행하지 않음
    - if~else if
        - 대등한 조건이 여러 개
    - 다중 if
        - if문 안에서 또 다른 조건식을 검사
    - switch~case
        - 조건식 선평가 후 case 상수와 일치하는 쪽으로 해석하여 명령문 실행
        - 조건식에서 비교 연산이 아닌 수식이나 값을 넣어야 함
        ![week5](https://github.com/yunh03/2_Group/blob/main/notes/src/week5.png)
2. 반복문
3. 무조건 분기문

### 조건 연산자
:피연산자가 3개인 삼항 연산자로, ? 와 : 연산자를 이용히여 프로그램 제어
- 작성 형식
    - `(문장1) ? (문장2) : (문장3);` 문장 1이 참이면 문장 2를 수행, 거짓이면 문장 3을 수행

- 큰 값, 작은 값
    - `max = ( x > y ) ? x : y;` `min = ( x > y ) ? y : x`
  


