[문제 바로가기](https://boj.kr/2577)

```c
#include <stdio.h>

int main(){
    int a, b, c, d;
    int nums[10] = {0,};

    scanf("%d", &a);
    scanf("%d", &b);
    scanf("%d", &c);

    d = a * b * c;

    while(d > 0){
        int num = d % 10;
        nums[num]++;
        d /= 10;
    }

    for(int i = 0; i < 10; i++){
        printf("%d\n", nums[i]);
    }

    return 0;
}
```