[문제 바로가기](https://boj.kr/1546)

```c
#include <stdio.h>

int main(){
    int count, max = 0;

    scanf("%d", &count);

    int nums[count];
    float values[count], sum = 0.0;

    for(int i = 0; i < count; i++){
        scanf("%d", nums + i);

        if(nums[i] > max){
            max = nums[i];
        }
    }

    for(int i = 0; i < count; i++){
        values[i] = (double)nums[i] / (double)max * 100;
        sum += values[i];
    }

    printf("%f", sum/count);

    return 0;
}
```