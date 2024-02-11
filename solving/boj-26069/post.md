[문제 바로가기](https://boj.kr/26069)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    map<string, bool> data;
    for(int i = 0; i < N; i++){
        string A, B;
        cin >> A >> B;

        if(A == "ChongChong" || B == "ChongChong"){
            data["ChongChong"] = true;
        }

        if(data[A] || data[B]){
            data[A] = true;
            data[B] = true;
        }
    }

    int ans = 0;
    for(auto iter = data.begin(); iter != data.end(); iter++){
        if(iter->second){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```