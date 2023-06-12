[문제 바로가기](https://boj.kr/11256)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int J, N;
        cin >> J >> N;

        vector<int> arr;
        for(int i = 0; i < N; i++){
            int R, C;
            cin >> R >> C;
            arr.push_back(R * C);
        }

        sort(arr.begin(), arr.end(), greater<int>());

        int sum = 0;
        for(int i = 0; i < N; i++){
            if(sum >= J){
                cout << i << "\n";
                break;
            }

            sum += arr[i];
        }
    }

    return 0;
}
```