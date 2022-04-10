[문제 바로가기](https://boj.kr/2675)

```c
#include <stdio.h>

int main() {
    int count;
    scanf("%d", &count);

    for(int i = 0; i < count; i++){
        char input[21];
        int num;

        scanf("%d", &num);
        scanf("%s", input);

        for(int j = 0; j < 21; j++){
            if(*(input + j) == '\0'){
                break;
            }
            for(int k = 0; k < num; k++){
                printf("%c", *(input + j));
            }
        }

        printf("\n");
    }
    
    return 0;
}
```