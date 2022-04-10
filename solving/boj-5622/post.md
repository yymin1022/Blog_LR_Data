[문제 바로가기](https://boj.kr/5622)

```c
#include <stdio.h>

int main()
{
	char input[16];
	int sum = 0;
	int nums[26] = {2, 2, 2, 3, 3, 3, 4, 4, 4, 5, 5, 5, 6, 6, 6, 7, 7, 7, 7, 8, 8, 8, 9, 9, 9, 9};

    scanf("%s", input);
	
    for(int i = 0; i < 16; i++){
        if(*(input + i) == '\0'){
            break;
        }

        sum += (nums[input[i] - 'A'] + 1);
    }
		
	printf("%d", sum);
    
    return 0;
}
```