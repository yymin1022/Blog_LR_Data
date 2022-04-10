[문제 바로가기](https://boj.kr/2742)

```c
#include <stdio.h>

int main() {
    int input;
    scanf("%d", &input);

    for(int i = input; i > 0; i--){
        printf("%d\n", i);
    }

    return 0;
}
```