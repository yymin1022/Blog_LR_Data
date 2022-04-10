[문제 바로가기](https://boj.kr/2908)

```c
#include <stdio.h>

int main() {
    char num1[4];
    char num2[4];

    scanf("%s", num1);
    scanf("%s", num2);

    if((int)(*(num1 + 2)) > (int)(*(num2 + 2))){
        printf("%c%c%c", num1[2], num1[1], num1[0]);
    }else if((int)(*(num1 + 2)) < (int)(*(num2 + 2))){
        printf("%c%c%c", num2[2], num2[1], num2[0]);
    }else{
        if((int)(*(num1 + 1)) > (int)(*(num2 + 1))){
            printf("%c%c%c", num1[2], num1[1], num1[0]);
        }else if((int)(*(num1 + 1)) < (int)(*(num2 + 1))){
            printf("%c%c%c", num2[2], num2[1], num2[0]);
        }else{
            if((int)(*(num1)) > (int)(*(num2))){
                printf("%c%c%c", num1[2], num1[1], num1[0]);
            }else if((int)(*(num1)) < (int)(*(num2))){
                printf("%c%c%c", num2[2], num2[1], num2[0]);
            }
        }
    }
    
    return 0;
}
```