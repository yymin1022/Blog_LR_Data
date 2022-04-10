[문제 바로가기](https://boj.kr/11720)

```c
#include <stdio.h>

int main() {
    int count, sum = 0;
    scanf("%d", &count);

    char input[count];
    scanf("%s", input);
    
    for(int i = 0; i < count; i++){
        sum += (int)*(input + i) - 48;
    }

    printf("%d", sum);
    
    return 0;
}
```