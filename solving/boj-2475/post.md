[문제 바로가기](https://boj.kr/2475)

```c
#include <stdio.h>

int main(){
    int num;
    int sum = 0;
    
    for(int i = 0; i < 5; i++){
        scanf("%d", &num);
        sum += (num * num);
    }
    
    printf("%d", sum % 10);
    
    return 0;
}
```