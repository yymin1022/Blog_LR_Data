[문제 바로가기](https://boj.kr/1157)

```c
#include <stdio.h>

int main() {
    char input[1000000];
    int count = 1;

    scanf("%[^\n]", input);

    if(*(input) == ' ' && *(input + 1) == '\0'){
        printf("0");

        return 0;
    }

    for(int i = 1; i < 1000001; i++){
        if(*(input + i) == '\0'){
            break;
        }

        if(*(input + i) == ' ' && *(input + i + 1) != '\0'){
            count++;
        }
    }

    printf("%d", count);
    
    return 0;
}
```