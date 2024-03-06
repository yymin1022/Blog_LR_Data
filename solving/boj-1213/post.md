[문제 바로가기](https://boj.kr/1213)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    vector<int> cnt(26, 0);
    for(int i = 0; i < S.size(); i++){
        cnt[S[i] - 'A']++;
    }

    int oddCnt = 0;
    for(int i = 0; i < 26; i++){
        oddCnt += cnt[i] % 2;
    }

    if(oddCnt > 1){
        cout << "I'm Sorry Hansoo" << "\n";
        return 0;
    }

    string ans;
    for(int i = 0; i < 26; i++){
        for(int j = 0; j < cnt[i] / 2; j++){
            ans.push_back(i + 'A');
        }
    }

    for(int i = 0; i < 26; i++){
        if(cnt[i] % 2){
            ans.push_back(i + 'A');
        }
    }

    for(int i = 25; i >= 0; i--){
        for(int j = 0; j < cnt[i] / 2; j++){
            ans.push_back(i + 'A');
        }
    }

    cout << ans <<'\n';

    return 0;
}
```