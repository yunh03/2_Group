### 수업 시간 중 나눈 질문들
**예제 4-9 - 변수의 특정 위치 비트 값 알아내기**

    A. lastmark와 firstmark는 무슨 역할을 할까?
    
    B. lastmark와 firstmark는 입력 받은 값을 특정 위치의 비트 값과 AND 연산을 해 해당 위치의 비트 값을 얻는데 사용한다.
    
    A. 그러면 lastmark는 마지막 비트를 얻기 위한 값이고 firstmark는 첫 번째 비트를 얻기 위한 값인건가?
    
    B. 그렇다.
    
    A. 그러면 왜 lastmark는 1이고, firstmark는 128인가?
    
    B. unsigned char 타입은 8비트를 가지기 때문에 마지막 비트를 확인하기 위해 10000000인 128이 필요하고, 첫 번째 비트를 확인하기 위해 00000001 인 1이 필요하다.

**2진수를 10진수로 되돌리기**

    A. 2진수로 표현된 값(1011)을 10진수로 어떻게 되돌리는가?
    
    B. 2진수의 값이 1011이라면 맨 오른쪽에 있는 숫자 0의 자리 값은 2의 0승이고 맨 오른쪽부터 왼쪽으로 2의 1승, 2의 2승, 2의 3승이 된다. 그러면, 그 자리에 있는 숫자와 자리 값을 곱한 값을 모두 더하면 10진수로 변환할 수 있다.
    
    A. 그러면 계산이 (1 * 2^3 + 0 * 2^2 + 1 * 2^1 + 1 * 2^0) 이렇게 해서 (8 + 0 + 2 + 1) 이 되어 11이 되는가?
    
    B. 그렇다. 2진수로 표현된 값의 맨 오른쪽 숫자의 자리 값이 2의 0승부터 시작된다는 것만 기억하면 2진수를 10진수로 쉽게 되돌릴 수 있다.

**10진수를 2진수로 변환하기**

    A. 그렇다면, 10진수를 2진수로 어떻게 변환하는가?
    
    B. 간단하다. 10진수의 숫자가 만약 11이라고 가정해보자.
    
    B. 11을 2로 나누면 몫이 5, 나머지가 1이다.
    
    B. 5를 2로 나누면 몫이 2, 나머지가 1이다.
    
    B. 2를 2로 나누면 몫이 1, 나머지가 0이다.
    
    B. 그러면 구한 마지막 몫의 숫자와 나머지를 거꾸로 읽으면, 1011이 된다.
    
    A. 그러면 만약에 2진수가 아니라 다른 진수의 값으로 되돌릴때도 똑같은 방법을 사용하는가?
    
    B. 그렇다. 다 똑같은 방법으로 계산하면 쉽다.

---

### 연산자란?

- 산술 연산자(+, -, *, /)와 같이 이미 정의된 연산을 수행하는 기호

### 연산자의 종류

1. 산술 연산자
    1. +, -, *, /, %
2. 관계 연산자
    1. >, <, ==, !=, >=, <=
3. 증감 연산자
    1. ++, --
        1. `a++` → 변수 값을 수식에 먼저 적용, 최종 변수 값 1 증가
        2. `++a` → 변수 값 1 증가 후 최종 변수 값 수식 적용
        3. `a--` → 변수 값 수식 적용 후 최종 변수 값 1 감소
        4. `--a` → 변수 값 1 감소 후 최종 변수 값 수식 적용
4. 논리 연산자
    1. &&, ||, !
    2. AND: &&
    3. OR: ||
    4. NOT: !
    5. 논리 연산자 우선순위
        1. ! > && > ||
5. 조건 연산자
    1. ?:
6. 비트 논리 연산자
    1. &, |, ^, ~
7. 비트 이동 연산자
    1. <<, >>
8. 대입 연산자
    1. =
    2. 프로그램에서 가장 기본이 되는 연산자

### lvalue(left value)

- 대입 연산자 기준, 왼쪽에 있는 피연산자 값, 변수, 수식 삽입 가능

### rvalue(right value)

대입 연산자 기준, 오른쪽에 있는 피연산자 변수만 삽입 가능

### 비트 연산자

- 1비트로는 데이터를 2개, 2비트로는 4개, n비트로는 2n개