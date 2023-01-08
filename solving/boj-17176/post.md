[문제 바로가기](https://boj.kr/17176)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> cnt(52, 0);
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        cnt[input]++;
    }

    string ans;
    cin.ignore();
    getline(cin, ans);

    for(int i = 0; i < ans.size(); i++){
        if(ans[i] == ' '){
            cnt[0]--;
            continue;
        }

        int tmp = ans[i] - 'A' + 1;
        if(tmp > 26){
            tmp -= 6;
        }

        cnt[tmp]--;
    }

    for(int i = 0; i < 52; i++){
        if(cnt[i] != 0){
            cout << "n" << "\n";
            return 0;
        }
    }

    cout << "y" << "\n";

    return 0;
}
```