[문제 바로가기](https://boj.kr/8958)

```c
#include <stdio.h>

int main(){
    int count;

    scanf("%d", &count);

    for(int i = 0; i < count; i++){
        char answer[80];
        int score = 0;
        int sum = 0;
        scanf("%s", answer);

        int j = 0;
        while(1){
            if(*(answer + j) == 'O'){
                score++;
            }else if(*(answer + j) == 'X'){
                for(int k = 1; k <= score; k++){
                    sum += k;
                }
                score = 0;
            }

            if(*(answer + j + 1) == '\0'){
                for(int k = 1; k <= score; k++){
                    sum += k;
                }
                break;
            }

            j++;
        }

        printf("%d\n", sum);
    }

    return 0;
}
```