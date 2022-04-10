[문제 바로가기](https://boj.kr/2562)

```c
#include <stdio.h>

int main(){
    int n[9], MAX, index;

    MAX = 0;

    for(int i = 0; i < 9; i++){
        scanf("%d", (n + i));

        if(n[i] > MAX){
            MAX = n[i];
            index = i + 1;
        }
    }

    printf("%d\n%d\n", MAX, index);

    return 0;
}
```