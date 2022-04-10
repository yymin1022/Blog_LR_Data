[문제 바로가기](https://boj.kr/10869)

```c
#include <stdio.h>

int main(){
    int a, b;

    scanf("%d %d", &a, &b);    
    printf("%d\n%d\n%d\n%d\n%d", a + b, a - b, a * b, a / b, a % b);

    return 0;
}
```