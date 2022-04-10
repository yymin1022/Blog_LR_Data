[문제 바로가기](https://boj.kr/10818)

```c
#include <stdio.h>

int main(){
    int n, MAX, MIN;
    
    scanf("%d", &n);

    int nums[n];

    for(int i = 0; i < n; i++){
        scanf("%d", (nums + i));

        if(i == 0){
            MAX = nums[0];
            MIN = nums[0];
        }else{
            if(MAX < nums[i]){
                MAX = nums[i];
            }
            if(MIN > nums[i]){
                MIN = nums[i];
            }
        }
    }

    printf("%d %d\n", MIN, MAX);

    return 0;
}
```