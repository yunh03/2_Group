# 3주차

## **2주차 수업에서 나눈 질문들**

**<math.h - pow>**

    A. math.h 함수는 무엇일까?

    B. 수학과 관련된 함수이다. 

    A. pow는 math.h의 어떤 함수에 속해있을까?

    B. power functions에 포함되어 있다.

    A. pow 함수의 정의는?

    B. x의 y거듭제곱을 반환하는 함수이다.

    A. 그러면 맨 위에 math.h 함수를 쓰지 않으면 pow 함수를 사용할 수 없는 걸까?

    B. 그럴 것 같다. 기본적으로 scanf 같은 함수도 stdio.h를 불러와서 사용하는데 stdio.h를 포함하지 않으면 사용할 수 없듯이 이 경우도 똑같이 적용될 것 같다.

**<예제 2-3>**

    A. float과 double이 가진 각각의 바이트 수는 무엇을 의미할까?

    B. double형은 8바이트로 64비트를,  float형은 4바이트로 32비트를 할당하기 때문에 double형이 더 큰 소수점 표현 범위를 가지고 있다. 따라서 double형의 정밀도가 더 높다. 

    A. 예제 2-3에서 double형과 float형에 20개의 소수점을 입력하여 출력했을 때, float형은 소수점 아래 8자리, double형은 소수점 아래 16자리부터 이상한 값이 출력된다.

    B. float은 표현할 수 있는 가장 근접한 수를 저장하여 약간의 오차 정도가 생긴 것 같은데, double형은 float보다 더 높은 정밀도와 큰 표현 범위를 가지고 있음에도 왜 오차가 생긴 걸까?

    A. double형 역시 부동소수점 방식으로 제한된 정밀도를 가지고 있어 근사값만을 표현하기 때문일 것이다. 그럼에도 float이나 double은 고정소수점 방식보다 넓은 범위의 수를 표현할 수 있어 과학적 계산이나 대용량 데이터 처리에 주로 사용된다고 한다.

    B. float과 double 모두 소수점을 고정하지 않는 부동소수점 방식이구나.
    
**<p71 1-2번>**

    A. 1번 문제는 숫자 입력을 받아야 하니까 char→int로 수정하면 되는데, 2번은 어디가 잘못된 거지?

    B. length가 소수점을 가진 수라서 length와 area앞을 short가 아닌 실수형의 기본형인 double로 수정해야 한다.

    A. 밑에서 number를 재정의해야 하니까, const도 지워서 실행해보자.

    B. const를 지우고 실행하니까 정상적으로 동작한다. 그러면 const는 값을 할당하고, 더 이상 변하지 않게 하는 것이 맞을까?

    A. 그렇다. 찾아보니까 const는 해당 포인터 변수가 가리키는 대상이 변하지 않도록 한다.

**<묵시적 형 변환 - 데이터 변환 방향>**

    A. 왜 데이터 변환 방향이 정해져있을까?

    B. 작은 범위에서 큰 범위로 변환을 해야 자료의 손실을 막을 수 있어서.

    A. 큰 범위에서 작은 범위로 변환하면?

    B. 값의 범위가 줄어들어 정보 손실이 발생할 수 있다.

    A. 그러면 자료형을 지정해 코드를 실행하는 것과 지정하지 않아서 묵시적 형 변환이 되어 실행하는 것 중에 어떤 것이 더 효율적일까?

    B. 자료형을 지정해 주는 것이 연산을 한번 줄여주기 때문에 더 좋지 않을까?

    A. 그럴 것 같다. 짧은 코드가 아니라 긴 코드가 포함된 무거운 파일이라면, 연산을 할 다른 코드도 많기에 이렇게 하나씩 연산을 줄여나가면 효율이 극대화될 것 같다.

---

## **2주차 수업 내용 정리**

p13~

### 자료형

: 선언된 변수들의 메모리를 할당하여 컴파일러에 전달

- **정수형**
    - `int`, `long`, `short`, `unsigned`
    - 소수점이 없는 숫자
    - 양수(+), 0, 음수(-)
        ![0](https://github.com/yunh03/2_Group/blob/main/notes/src/0.png?raw=true)
    - 같은 short라도 바이트 수가 상이
    - 허용 범위를 넘는 값을 저장할 경우 전혀 다른 값이 저장되는 오버플로(overflow) 발생
    
- **실수형**
    - `float`, `double`(기본형)
    - 소수점이나 지수가 있는 수
    - 출력 시 변환 기호가 존재 float→ `%f` / double → `%lf`
    - 변환 기호에 따라 바이트 수가 상이 float →4B /  double, long double →8B
    - 출력값 조정
      
        ![1](https://github.com/yunh03/2_Group/blob/main/notes/src/1.png?raw=true)
        
    
- **문자형**
    - `char`
    - 문자를 작은 따옴표 안에 넣어서 사용
    - 내부 문자 코드에 상응하는 숫자로 변환하여 기억
    - 0~127의 부호 없는 정수에 문자를 정의
    - 출력값 조정

       ![2](https://github.com/yunh03/2_Group/blob/main/notes/src/2.png?raw=true)
    - C언어에서 다루는 문자 표현
        
        ![3](https://github.com/yunh03/2_Group/blob/main/notes/src/3.png?raw=true)
        `\n`, `\r`은 꼭 알아두기
        
    - 아스키 코드 표현
        
        ![4](https://github.com/yunh03/2_Group/blob/main/notes/src/4.png?raw=true)
        ![5](https://github.com/yunh03/2_Group/blob/main/notes/src/5.png?raw=true)
      Dec : 정수 표현 / Hex : 16진수 표현
        
- **복합형**
    - `array`, `struct`, `union`, `enum`

### 형 변환

: 자료형을 바꾸는 것

- 묵시적 형 변환
    - 컴파일러가 자동으로 수행
    - 데이터의 값을 잃지 않는 방향으로 실행
- 명시적 형 변환
    - 사용자가 강제로 지정
    - 캐스팅 연산자를 사용
    - 연산식 앞에 `()`, 괄호 안에는 변환할 자료형을 입력

### 입출력 함수의 종류

- 표준 입출력 함수
    - 기본 입출력 장치인 키보드와 모니터로 자료를 입출력하는 함수
    - 형식화된 입출력 → `scan()`, `printf()`
    - 문자 입출력  → `getchar()`, `putchar()`
    - 문자열 입출력 → `gets()`, `puts()`
- 파일 입출력 함수
    - 파일을 이용하여 자료를 입출력하는 함수
- 저급 입출력 함수
    - 운영 프로그램에서 제공된 함수가 아닌 운영체제 내의 시스템 호출을 통해 입출력하는 함수

### 형식화된 입출력

- printf() 함수
    - 표준 출력장치인 모니터로 자료를 출력하는 함수
    - 기본 형식 → `print(”문자열”)` , `printf(”제어 문자열”, 변수/표현식);`
    - 변환기호 → 제어 문자열에 변환기호를 추가하면 대응하는 값을 형식에 따라 출력
        ![6](https://github.com/yunh03/2_Group/blob/main/notes/src/6.png?raw=true)
    - 표현식의 관계
        ![7](https://github.com/yunh03/2_Group/blob/main/notes/src/7.png?raw=true)

- scanf() 함수
    - 표준 입력장치인 키보드를 통해 자료를 읽는 함수
    - 기본 형식 → `scanf(”변환기호”, &변수1, &변수2,…);`
    - 변환기호와 변수의 관계
        ![8](https://github.com/yunh03/2_Group/blob/main/notes/src/8.png?raw=true)
    - 변수 앞에 변수의 주소값인 `&`를 반드시 포함
- 탈출 기법
    - 표현 방법이 없거나 특수문자를 입력할 때 사용
- 문자 입출력
    - 문자 1개를 키보드로 입력받아 출력하는 함수
    - 문자 입력 → `getchars()` / 문자 출력 → `putchar()`
- 문자열 입출력
    - 문자 여러 개를 한 번에 입력받아 출력하는 함수
    - 공백문자가 포함된 입력 시 → `gets()` / 표준 출력장치로 된 출력 시 → `puts()`


