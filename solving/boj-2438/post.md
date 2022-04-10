[문제 바로가기](https://boj.kr/2438)

```c
#include <stdio.h>

int main() {
    int input;
    scanf("%d", &input);

    for(int i = 1; i <= input; i++){
        for(int j = 0; j < i; j++){
            printf("*");
        }
        printf("\n");
    }

    return 0;
}
```