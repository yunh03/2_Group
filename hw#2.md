1. 책 정보를 담을 수 있는 구조체 배열 및 기능이 구현된 코드

```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

#define SIZE 5

typedef struct {
    char title[50];
    char author[50];
    char press[50];
    int page;
    int price;
    char borrow[10];
} Book;

Book library[SIZE] = {
    {"Truth", "John", "Century", 300, 20000, "available"},
    {"Love", "Paul", "Goods", 200, 15000, "available"},
    {"Joy", "James", "Cookie", 250, 18000, "available"},
    {"Thanks", "Mark", "Saejong", 240, 21000, "available"},
    {"God", "Johnson", "Jungjo", 450, 35000, "available"}
};

void list_books() {
    printf("Title\tAuthors\tPress\tPage\tPrice\n");
    printf("-----\t-------\t-----\t----\t-----\n");
    for(int i=0; i<SIZE; i++) {
        printf("%s\t%s\t%s\t%d\t%d\n", library[i].title, library[i].author, library[i].press, library[i].page, library[i].price);
    }
}

int find_book(char *title) {
    for(int i=0; i<SIZE; i++) {
        if(strcasecmp(library[i].title, title) == 0)
            return i;
    }
    return -1;
}

void search_book() {
    char title[50];
    printf("검색 할 도서를 입력하세요: ");
    scanf("%s", title);
    int index = find_book(title);
    if(index != -1) {
        printf("Title\tAuthors\tPress\tPage\tPrice\tBorrow\n");
        printf("-----\t-------\t-----\t----\t-----\t------\n");
        printf("%s\t%s\t%s\t%d\t%d\t%s\n", library[index].title, library[index].author, library[index].press, library[index].page, library[index].price, library[index].borrow);
    } else {
        printf("보유하고 있지 않은 책입니다.\n");
    }
}

void borrow_book() {
    char title[50];
    printf("대출을 원하는 책 제목을 입력하세요: ");
    scanf("%s", title);
    int index = find_book(title);
    if(index != -1) {
        if(strcmp(library[index].borrow, "available") == 0) {
            strcpy(library[index].borrow, "borrowing");
            printf("대출이 완료되었습니다.\n");
            printf("Title\tAuthors\tPress\tPage\tPrice\tBorrow\n");
            printf("-----\t-------\t-----\t----\t-----\t------\n");
            printf("%s\t%s\t%s\t%d\t%d\t%s\n", library[index].title, library[index].author, library[index].press, library[index].page, library[index].price, library[index].borrow);
        } else {
            printf("이미 대출이 완료된 책입니다..\n");
            printf("Title\tAuthors\tPress\tPage\tPrice\tBorrow\n");
            printf("-----\t-------\t-----\t----\t-----\t------\n");
            printf("%s\t%s\t%s\t%d\t%d\t%s\n", library[index].title, library[index].author, library[index].press, library[index].page, library[index].price, library[index].borrow);
        }
    } else {
        printf("존재하지 않는 책입니다.\n");
    }
}

void return_book() {
    char title[50];
    printf("반납 할 책 제목을 입력하세요: ");
    scanf("%s", title);
    int index = find_book(title);
    if(index != -1) {
        if(strcmp(library[index].borrow, "borrowing") == 0) {
            strcpy(library[index].borrow, "available");
            printf("책 반납이 완료되었습니다.\n");
            printf("Title\tAuthors\tPress\tPage\tPrice\tBorrow\n");
            printf("-----\t-------\t-----\t----\t-----\t------\n");
            printf("%s\t%s\t%s\t%d\t%d\t%s\n", library[index].title, library[index].author, library[index].press, library[index].page, library[index].price, library[index].borrow);
        } else {
            printf("대출되지 않은 도서입니다. 반납할 수 없습니다\n");
            printf("Title\tAuthors\tPress\tPage\tPrice\tBorrow\n");
            printf("-----\t-------\t-----\t----\t-----\t------\n");
            printf("%s\t%s\t%s\t%d\t%d\t%s\n", library[index].title, library[index].author, library[index].press, library[index].page, library[index].price, library[index].borrow);
        }
    } else {
        printf("존재하지 않는 책입니다.\n");
    }
}

int main() {
    int choice;
    while(1) {
        printf("1. 도서목록\n2. 검색\n3. 대출\n4. 반납\n5. 종료\n메뉴를 선택하세요: ");
        scanf("%d", &choice);
        switch(choice) {
            case 1:
                list_books();
                break;
            case 2:
                search_book();
                break;
            case 3:
                borrow_book();
                break;
            case 4:
                return_book();
                break;
            case 5:
                return 0;
            default:
                printf("사용할 수 없는 메뉴입니다.\n");
        }
    }
    return 0;
}
```
2. 실행 결과 화면

![result1](https://github.com/yunh03/2_Group/blob/main/notes/src/hw2-1.png?raw=true)
![result2](https://github.com/yunh03/2_Group/blob/main/notes/src/hw2-2.png?raw=true)
![result3](https://github.com/yunh03/2_Group/blob/main/notes/src/hw2-3.png?raw=true)
![result4](https://github.com/yunh03/2_Group/blob/main/notes/src/hw2-4.png?raw=true)
![result5](https://github.com/yunh03/2_Group/blob/main/notes/src/hw2-5.png?raw=true)
![result6](https://github.com/yunh03/2_Group/blob/main/notes/src/hw2-6.png?raw=true)
![result7](https://github.com/yunh03/2_Group/blob/main/notes/src/hw2-7.png?raw=true)
