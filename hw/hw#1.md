1. 최대, 최소, 내림차순 정렬이 구현된 코드
```
#include <stdio.h>

int Max(int* pArr, int size) {
    int max = pArr[0];
    
    for(int i = 0; i < size; i++) {
        if(pArr[i] > max) {
            max = pArr[i];
        }
    }

    return max;
}

int Min(int* pArr, int size) {
    int min = pArr[0];
    
    for(int i = 0; i < size; i++) {
        if(pArr[i] < min) {
            min = pArr[i];
        }
    }

    return min;
}

void swap(int* a, int* b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

void Sorting(int* pArr, int size) {
    for(int i = 0; i < size - 1; i++) {
        for(int j = 0; j < size - i - 1; j++) {
            if(pArr[j] < pArr[j + 1]) {
                swap(&pArr[j], &pArr[j + 1]);
            }
        }
    }
}

int main(void) {
    int a[] = {20, 34, 12, 24, 54, 91, 9, 40, 81, 10};
    printf("배열 최대 값: %d \n", Max(a, sizeof(a) / sizeof(int)));
    printf("배열 최소 값: %d \n", Min(a, sizeof(a) / sizeof(int)));
    Sorting(a, sizeof(a) / sizeof(int));
    printf("내림차순 정렬: ");
    for(int i = 0; i < sizeof(a) / sizeof(int); i++) {
        printf("%d ", a[i]);
    }
    return 0;
}
```

---

2. 실행 결과

![result](https://raw.githubusercontent.com/yunh03/2_Group/main/notes/src/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202023-11-18%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%201.17.20.png)
