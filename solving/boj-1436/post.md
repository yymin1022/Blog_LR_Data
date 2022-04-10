[문제 바로가기](https://boj.kr/1436)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int count = 0;
    for(int num = 666; ; num++){
        int temp = num;

        while(temp){
            if(temp % 1000 == 666){
                count++;
                break;
            }

            temp /= 10;
        }

        if(count == N){
            cout << num << "\n";
            break;
        }
    }

    return 0;
}
```