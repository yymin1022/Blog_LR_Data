[문제 바로가기](https://boj.kr/10952)

```c
#include <stdio.h>

int main(){
    int a, b;
    
    while(1){
        scanf("%d %d", &a, &b);
        
        if(a == 0 && b == 0){
            break;
        }
        
        printf("%d\n", a + b);
    }
    
    return 0;
}
```