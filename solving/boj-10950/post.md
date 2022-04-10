[문제 바로가기](https://boj.kr/10950)

```c
#include <stdio.h>

int main(void){
    int num, num1, num2;
    scanf("%d", &num);

    for(int i = 0; i < num; i++){
        scanf("%d %d", &num1, &num2);
        printf("%d\n", num1 + num2);
    }
    
    return 0;
}
```