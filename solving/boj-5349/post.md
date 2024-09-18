[문제 바로가기](https://boj.kr/5349)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    map<string, int> SSN;
    vector<string> ans;
    while(true){
        string S;
        cin >> S;

        if(S == "000-00-0000"){
            break;
        }

        if(SSN[S] == 1){
            ans.push_back(S);
        }
        SSN[S]++;
    }

    sort(ans.begin(), ans.end());

    for(int i = 0; i < ans.size(); i++){
        cout << ans[i] << "\n";
    }

    return 0;
}

```