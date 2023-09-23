# 3주차

## **2주차 수업에서 나눈 질문들**

**<math.h - pow>**

A. math.h 함수는 무엇일까?

B. 수학과 관련된 함수이다. 

B. pow는 math.h의 어떤 함수에 속해 있지?

A. power functions에 포함되어 있다.

B. pow 함수의 정의는?

A. x의 y거듭제곱을 반환하는 함수이다.

**<예제 2-3>**

float에서 정수형과 실수형을 신경 써서 

A. float과 double가 가진 각각의 바이트 수는 무엇을 의미할까?

B. double형은 8바이트로 64비트를,  float형은 4바이트로 32비트를 할당하기 때문에 double형이 

더 큰 소수점 표현 범위를 가지고 있다. 따라서 double형의 정밀도가 더 높다. 

A. 예제 2-3에서 double형과 float형에 15개의 소수점을 입력하여 출력했을 때, float형은 소수점 아

래 8자리부터 이상한 값이 출력된다.

**<p71 1-2번>**

A. 1번 문제는 숫자 입력을 받아야 하니까 char→int로 수정하면 되는데, 2번은 어디가 잘못된 거지?

B. length가 소수점을 가진 수라서 length와 area앞을 short가 아닌 실수형의 기본형인 double로 수

정해야 한다.

A. 밑에서 number를 재정의해야 하니까, const도 지워서 실행해보자.

**<묵시적 형 변환 - 데이터 변환 방향>**

A. 왜 데이터 변환 방향이 정해져있을까?

B. 작은 범위에서 큰 범위로 변환을 해야 자료의 손실을 막을 수 있어서.

A. 큰 범위에서 작은 범위로 변환하면?

B. 값의 범위가 줄어들어 정보 손실이 발생할 수 있다.

---

## **2주차 수업 내용 정리**

p13~

### 자료형

: 선언된 변수들의 메모리를 할당하여 컴파일러에 전달

- **정수형**
    - int, long, short, unsigned
    - 소수점이 없는 숫자
    - 양수(+), 0, 음수(-)
    
    ![스크린샷 2023-09-21 오후 6.39.48.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/6e4bf9dd-346a-4b68-87ba-b42c12297443/ba156219-b051-46ad-bca2-1a884a1c7001/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2023-09-21_%EC%98%A4%ED%9B%84_6.39.48.png)
    
    - 같은 short라도 바이트 수가 상이
    - 허용 범위를 넘는 값을 저장할 경우 전혀 다른 값이 저장되는 오버플로(overflow) 발생
    
- **실수형**
    - float, double(기본형)
    - 소수점이나 지수가 있는 수
    - 출력 시 변환 기호가 존재 float→ %f / double → %lf
    - 변환 기호에 따라 바이트 수가 상이 float →4B /  double, long double →8B
    - 출력값 조정
        
        ![스크린샷 2023-09-21 오후 6.50.17.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/6e4bf9dd-346a-4b68-87ba-b42c12297443/e1ad0bfa-fbf6-4df5-bfbd-6f78825cd839/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2023-09-21_%EC%98%A4%ED%9B%84_6.50.17.png)
        
    
- **문자형**
    - char
    - 문자를 작은 따옴표 안에 넣어서 사용
    - 내부 문자 코드에 상응하는 숫자로 변환하여 기억
    - 0~127의 부호 없는 정수에 문자를 정의
    - 출력값 조정
        
        ![스크린샷 2023-09-21 오후 6.52.47.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/6e4bf9dd-346a-4b68-87ba-b42c12297443/8ea47698-baef-4afb-b842-d4b0c95ea3f9/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2023-09-21_%EC%98%A4%ED%9B%84_6.52.47.png)
        
    - C언어에서 다루는 문자 표현
        
        ![\n, \r은 꼭 알아두기](https://prod-files-secure.s3.us-west-2.amazonaws.com/6e4bf9dd-346a-4b68-87ba-b42c12297443/2d85ee07-0178-48e2-ba28-ec0f13bc84ae/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2023-09-21_%EC%98%A4%ED%9B%84_6.55.46.png)
        
        \n, \r은 꼭 알아두기
        
    - 아스키 코드 표현
        
        ![  Dec : 정수 표현 / Hex : 16진수 표현](https://prod-files-secure.s3.us-west-2.amazonaws.com/6e4bf9dd-346a-4b68-87ba-b42c12297443/cffb7260-e3cb-4d7d-923e-6e450dcef951/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2023-09-21_%EC%98%A4%ED%9B%84_6.55.55.png)
        
          Dec : 정수 표현 / Hex : 16진수 표현
        
        ![스크린샷 2023-09-21 오후 6.58.39.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/6e4bf9dd-346a-4b68-87ba-b42c12297443/8288535b-9414-46a6-a47d-d903c18d83dc/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2023-09-21_%EC%98%A4%ED%9B%84_6.58.39.png)
        

- **복합형**
    - array, struct, union, enum

### 형 변환

: 자료형을 바꾸는 것

- 묵시적 형 변환
    - 컴파일러가 자동으로 수행
    - 데이터의 값을 잃지 않는 방향으로 실행
- 명시적 형 변환
    - 사용자가 강제로 지정
    - 캐스팅 연산자를 사용
    - 연산식 앞에 (), 괄호 안에는 변환할 자료형을 입력

### 입출력 함수의 종류

- 표준 입출력 함수
    - 기본 입출력 장치인 키보드와 모니터로 자료를 입출력하는 함수
    - 형식화된 입출력 → scan(), printf()
    - 문자 입출력  → getchar(), putchar()
    - 문자열 입출력 → gets(), puts()
- 파일 입출력 함수
    - 파일을 이용하여 자료를 입출력하는 함수
- 저급 입출력 함수
    - 운영 프로그램에서 제공된 함수가 아닌 운영체제 내의 시스템 호출을 통해 입출력하는 함수

### 형식화된 입출력

- printf() 함수
    - 표준 출력장치인 모니터로 자료를 출력하는 함수
    - 기본 형식 → print(”문자열”) , printf(”제어 문자열”, 변수/표현식);
    - 변환기호 → 제어 문자열에 변환기호를 추가하면 대응하는 값을 형식에 따라 출력
        
        ![스크린샷 2023-09-21 오후 7.26.37.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/6e4bf9dd-346a-4b68-87ba-b42c12297443/16165b34-2576-4d22-97d4-1750bfb59e54/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2023-09-21_%EC%98%A4%ED%9B%84_7.26.37.png)
        
    - 표현식의 관계

![스크린샷 2023-09-23 오전 1.56.45.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/6e4bf9dd-346a-4b68-87ba-b42c12297443/d41f489a-2059-4aab-8ecb-02607364f835/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2023-09-23_%EC%98%A4%EC%A0%84_1.56.45.png)

- scanf() 함수
    - 표준 입력장치인 키보드를 통해 자료를 읽는 함수
    - 기본 형식 → scans(”변환기호”, &변수1, &변수2,…);
    - 변환기호와 변수의 관계
        
        ![스크린샷 2023-09-23 오전 2.06.37.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/6e4bf9dd-346a-4b68-87ba-b42c12297443/37e93b7b-694b-4350-aeb7-1c511e990bb5/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2023-09-23_%EC%98%A4%EC%A0%84_2.06.37.png)
        
    - 변수 앞에 변수의 주소값인 &를 반드시 포함
- 탈출 기법
    - 표현 방법이 없거나 특수문자를 입력할 때 사용
- 문자 입출력
    - 문자 1개를 키보드로 입력받아 출력하는 함수
    - 문자 입력 → getchars() / 문자 출력 → put char()
- 문자열 입출력
    - 문자 여러 개를 한 번에 입력받아 출력하는 함수
    - 공백문자가 포함된 입력 시 → gets() / 표준 출력장치로 된 출력 시 → puts()


