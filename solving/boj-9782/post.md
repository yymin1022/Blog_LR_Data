[문제 바로가기](https://boj.kr/9782)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int idx = 1;
    while(N){
        vector<float> arr(N);
        for(int i = 0; i < N; i++){
            cin >> arr[i];
        }

        cout << "Case " << idx << ": ";
        cout << fixed;
        cout.precision(1);
        if(N % 2){
            cout << arr[N / 2] << "\n";
        }else{
            cout << (arr[N / 2 - 1] + arr[N / 2]) / 2 << "\n";
        }

        cin >> N;
        idx++;
    }

    return 0;
}
```