[문제 바로가기](https://boj.kr/4518)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    while(N && M){
        vector<bool> CD(1000000001, false);
        for(int i = 0; i < N; i++){
            int num;
            cin >> num;
            CD[num] = true;
        }

        int cnt = 0;
        for(int i = 0; i < M; i++){
            int num;
            cin >> num;
            if(CD[num]){
                cnt++;
            }
        }

        cout << cnt << "\n";

        cin >> N >> M;
    }


    return 0;
}
```