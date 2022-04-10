[문제 바로가기](https://boj.kr/1330)

```c
#include <stdio.h>

int main(){
    int a, b;
    
    scanf("%d %d", &a, &b);
    
    if(a > b){
        printf(">");
    }else if(a < b){
        printf("<");
    }else{
        printf("==");
    }

    return 0;
}
```