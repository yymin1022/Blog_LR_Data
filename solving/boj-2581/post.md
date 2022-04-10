[문제 바로가기](https://boj.kr/2581)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int M, N;
    cin >> M >> N;

    int minM = 10000;
    int sum = 0;

    for(int i = M; i <= N; i++){
        bool isOK = true;
        if(i < 2){
            isOK = false;
        }
        for(int j = 2; j <= sqrt(i); j++){
            if(i % j == 0){
                isOK = false;
                break;
            }
        }

        if(isOK){
            minM = min(minM, i);
            sum += i;
        }
    }

    if(!sum){
        cout << -1 << "\n";
    }else{
        cout << sum << "\n" << minM << "\n";
    }

    return 0;
}
```