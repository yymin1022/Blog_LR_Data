[문제 바로가기](https://boj.kr/3060)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        int ans = 0;
        int sum = 0;
        vector<int> pig;
        for(int i = 0; i < 6; i++){
            int input;
            cin >> input;
            pig.push_back(input);
            sum += input;
        }

        while(sum <= N){
            ans++;
            sum *= 4;
        }

        cout << ans + 1 << "\n";
    }
    
    return 0;
}
```