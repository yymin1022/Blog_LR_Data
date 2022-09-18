[문제 바로가기](https://boj.kr/1786)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string T, P;
    getline(cin, T);
    getline(cin, P);

    vector<int> pi(P.size(), 0);
    for(int i = 1, j = 0; i < P.size(); i++){
        while(j > 0 && P[i] !=  P[j]){
            j = pi[j-1];
        }

        if(P[i] == P[j]){
            j++;
            pi[i] = j;
        }
    }

    vector<int> ans;
    for(int i = 0, j = 0; i < T.size(); i++){
        while(j > 0 && T[i] != P[j]){
            j = pi[j - 1];
        }

        if(T[i] == P[j]){
            if(j == P.size() - 1){
                ans.push_back(i - P.size()+1);
                j = pi[j];
            }else{
                j++;
            }
        }
    }

    cout << ans.size() << "\n";

    for(int i : ans){
        cout << i + 1 << "\n";
    }

    return 0;
}
```