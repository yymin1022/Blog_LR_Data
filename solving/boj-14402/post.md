[문제 바로가기](https://boj.kr/14402)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    map<string, int> data;
    for(int i = 0; i < N; i++){
        string A, B;
        cin >> A >> B;

        if(B == "+"){
            data[A]++;
        }else if(data[A]){
            data[A]--;
        }else{
            ans++;
        }
    }

    for(auto iter = data.begin(); iter != data.end(); iter++){
        ans += iter->second;
    }

    cout << ans << "\n";

    return 0;
}
```