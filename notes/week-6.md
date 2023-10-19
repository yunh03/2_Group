## 수업시간 중 나눈 질문

### for문

```
A. for문은 어떻게 쓰는걸까?
B. for()하고 괄호 안에, 초기화, 조건식, 증감식을 적으면 돼.
A. 그러면 5번을 실행하고 싶으면 어떻게 할까?
B. 초기화 조건에 'int i = 0;'을 적고, 조건식에 'i < 5;'를 적고 한 번 실행될 때마다 i가 1씩 증가하는 i++를 적으면 돼.
A. 근데 5번을 실행하는데 i가 5보다 작을까?
B. i가 0부터 증가하고 1씩 증가하니까, 0, 1, 2, 3, 4 이렇게 5번이 실행되기 때문이야.
A. 그러면 만약 i가 1이라면, 조건식에 i <= 5를 하면 되겠네?
B. 맞아.
```

### **for문 - 알파벳 출력하기**

```
A. 알파벳, 즉 그 문자를 출력하는데 왜 i에 숫자가 들어갈까?
B. 아스키코드에 관한 숫자이다.
A. 대문자 A의 아스키 코드 숫자가 65인가?
B. 그렇다. 대문자 A의 아스키 코드 숫자는 65이다.
B. A, B, C, D 순차적으로 알파벳이 올라갈 수록 아스키 코드의 숫자가 1씩 올라간다.
A. 그러면 i가 90이하까지 반복문이 동작하니까, 마지막 Z의 아스키 코드는 90인가?
B. 그렇다.
A. 그러면 소문자 a부터 z까지는 어떻게 표현할까?
B. 소문자 a의 아스키 코드는 97이고, 소문 z의 아스키 코드는 122이다.
A. 그러면 반복문을 수정해 보면, i는 97부터 시작하고, 조건식을 i는 122 이하까지로 변경하면 될까?
B. 그렇다. 그렇게 수정하면 소문자 a부터 z까지의 문자가 정상적으로 출력될 것 같다.
```

### 다중 for문

```
A. 다중 for문이 for문을 여러번 쓰는 것을 말하는 것일까?
B. 그렇다 for문 안에 for문을 한 번 더 쓸 수 있다.
A. 그러면 다중 for문을 사용하면 어떤 식으로 for문이 동작하는가?
B. 바깥쪽 for 문의 조건이 한 번 실행될 때, 안에 있는 for문이 실행된다.
A. 그러면 안에 있는 for문의 실행이 끝나면 바깥쪽 실행문이 다시 실행되는 것일까?
B. 그럴 것 같다. 안에서 할 일을 끝낸다면 바깥쪽 for문으로 다시 넘어가 나머지 처리를 해야하기 때문이다.

```

### 다중 for문 - 1에서 100 사이의 소수 구하기

```
A. 소수의 정의를 하고 시작해 보자.
B. 소수는 1과 자기 자신으로 밖에 나누어지지 않는 수를 얘기한다.
A. 그러면 1부터 100까지의 소수를 구해야 하고, 5개마다 줄 바꿈을 해야하니, count라는 정수형 변수를 하나 사용하자.
B. 그러면 1은 소수가 아님으로, 초기 값을 i는 2로 시작하고, 100 이하까지의 조건을 넣자.
B. 그리고 한 번 명령문이 실행되면 i에 1이 더해질 수 있도록 i++을 추가하자.
A. 그러면 일단 i가 100까지 모두 돌 수 있겠다.
B. 이제 for문 안쪽에 소수를 구별해 내는 for문을 적어보자.
A. 바깥쪽 for문의 변수를 i로 설정했으니까 안쪽 for문은 j로 설정하자.
A. j는 i의 숫자가 바뀔 때마다 초기화 되어야 하니까 이중 for문을 작성하기 이전에 int j로 변수를 지정하자.
B. 그러면 j를 초기화 하는걸 작성했으니까, j는 i와 동일하게 2부터 시작하고, i보다 작을 떄까지만을 조건으로 하자.
B. 그리고 한 번 실행될 때마다 j의 값이 1 증가하게 했어.
A. 좋아. 그러면 소수의 조건인 자기 자신의 숫자 이외에 다른 숫자로 나눠지면 조건문 실행을 중단하고, 2번째 for문 밖에 소수의 마지막 조건인 자기 자신인지, 즉, i와 j가 같은 값인지 확인하는 조건을 추가하자.
B. 그러면, 마지막으로 5개가 나왔을 때 한 줄 띄우는거는 소수를 하나 발견할 때마다 count가 1씩 증가하기 때문에 count가 5를 넘었을 때 줄 바꿈을 하는걸로 하자.
B. 그리고 count를 0으로 초기화하자.
```

## 내용 정리

### 반복문

- 동일한 내용을 반복하거나, 일정한 규칙으로 반복하는 일을 수행할 때 사용
- 프로그램 → 조금 더 간결, 실제적

### for

- 특정한 문장 → 일정한 횟수만큼 반복시킬 때 사용

```c
for(초기화; 조건식; 증감식) {
	명령문 1;
	명령문 2;
}
```

1. 초기화
    1. 변수의 초기 값 저장
    2. 반복문의 시작
2. 조건식
    1. 변수 값이 조건식에 맞으면 계속 반복
3. 증감식
    1. 식에 따라 변수 값을 증가시키거나 감소시킴
4. 명령문
    1. 조건식이 참이면 명령문 수행
- 실행 순서: 초기화 → 조건식 → 명령문 → 증감식 → 조건식 → 명령문 → 증감식

### 다중 for

- for문이 2개 이상인 것
- 실행 순서나 형식은 단일 for문과 같음

```c
for(초기화; 조건식; 증감식) {
	for(초기화; 조건식; 증감식) {
		명령문 1;
	}
}
```

### while

- for문은 횟수를 정확히 알고 있을 때 사용했다면, while문은 횟수를 정확하지 알지 못하지만 반복의 조건을 알고 있을 때 사용

```c
while(조건식) {
	명령문 1;
	명령문 2;
	
	증감식;
}
```

### while과 for의 초기화 위치 비교

- for: 반복문 안에서 초기화
    - for문 시작 전에 초기화를 시작할 수 있지만, 일반적으로 사용되지 않는 방법임
- while: 반복문 외부에서 초기화

### do~while

- 먼저 do 안에 있는 명령문 수행 → while문 조건식 비교
- 적어도 한 번은 명령문을 처리함
- 마지막에 세미콜론(;) 필수

```c
do {
	명령문 1;
} while(조건식);
```

### goto

- 명령문의 실행 순서를 임의로 변경하고자 할 때 사용
- 라벨은 다른 명령문 앞에 선언, 라벨 다음에 콜론(:)을 넣음
- 일반적으로 잘 사용되지 않는 방법

```c
goto Label:
```

### break

- 반복문을 빠져나오거나, `switch~case` 문에서 정상적 흐름을 변경하기 위해 사용
- 주로 `goto`문 대신에 쓰는 방법, `switch~case` 문에서는 필수적으로 사용 됨

### continue

- 반복문을 빠져나오지 않고, 해당 반복문의 처음으로 프로그램의 흐름을 이어나감