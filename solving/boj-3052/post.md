[문제 바로가기](https://boj.kr/3052)

```c
#include <stdio.h>

int main(){
    int nums[10];
    int result = 0;

    for(int i = 0; i < 10; i++){
        int num;
        scanf("%d", &num);

        nums[i] = num % 42;
    }

    for(int i = 0; i < 10; i++){
        int count = 0;
        for(int j = i + 1; j < 10; j++){
            if(nums[i] == nums[j]){
                count++;
            }
        }

        if(count == 0){
            result++;
        }
    }

    printf("%d", result);

    return 0;
}
```