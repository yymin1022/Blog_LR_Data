[문제 바로가기](https://boj.kr/1515)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    int ans = 0;
    int idx = 0;
    while(ans++ < 30000){
        string tmp = to_string(ans);
        for(int i = 0; i < tmp.length(); i++){
            if(S[idx] == tmp[i]){
                idx++;
            }

            if(idx == S.length()){
                cout << ans << "\n";
                return 0;
            }
        }
    }

    return 0;
}

```