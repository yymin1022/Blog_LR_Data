[문제 바로가기](https://boj.kr/4344)

```c
#include <stdio.h>

int main(){
    int count;

    scanf("%d", &count);

    for(int i = 0; i < count; i++){
        int num, sum = 0;
        scanf("%d", &num);

        int score[num];
        for(int j = 0; j < num; j++){
            scanf("%d", score + j);
            sum += score[j];
        }

        float avg = (double)sum / (double)num;
        int students = 0;

        for(int j = 0; j < num; j++){
            if(score[j] > avg){
                students++;
            }
        }

        printf("%.3f%%\n", (double)students / (double)num * 100);
    }

    return 0;
}
```