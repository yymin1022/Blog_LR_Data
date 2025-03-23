[문제 바로가기](https://boj.kr/10448)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    for(int i = 1; i <= 1000; i++){
        arr[i] = arr[i - 1] + i;
    }

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        bool flag = false;
        for(int i = 1; i <= 50; i++){
            for(int j = 1; j <= 50; j++){
                for(int k = 1; k <= 50; k++){
                    if(arr[i] + arr[j] + arr[k] == N){
                        flag = true;
                        i = 100;
                        j = 100;
                        k = 100;
                    }
                }
            }
        }

        cout << (flag ? 1 : 0) << "\n";
    }

    return 0;
}
```