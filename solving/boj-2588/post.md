[문제 바로가기](https://boj.kr/2588)

```c
#include <stdio.h>

int main(){
    int a, b;

    scanf("%d %d", &a, &b);
    
    int d, e, f;
    f = b / 100;
    e = (b % 100) / 10;
    d = b % 10;
    
    printf("%d\n%d\n%d\n%d", a * d, a * e, a * f, a * b);

    return 0;
}
```