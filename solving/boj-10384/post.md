[문제 바로가기](https://boj.kr/10384)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;
    cin.ignore();

    for(int i = 1; i <= N; i++){
        string S;
        getline(cin, S);

        vector<int> cnt(26, 0);
        for(int j = 0; j < S.size(); j++){
            if(S[j] >= 'A' && S[j] <= 'Z'){
                cnt[S[j] - 'A']++;
            }else if(S[j] >= 'a' && S[j] <= 'z'){
                cnt[S[j] - 'a']++;
            }
        }

        int tmp = 5;
        for(int j = 1; j < 26; j++){
            tmp = min(cnt[j], tmp);
        }

        switch(tmp){
            case 1:
                cout << "Case " << i << ": Pangram!" << "\n";
                break;
            case 2:
                cout << "Case " << i << ": Double pangram!!" << "\n";
                break;
            case 3:
                cout << "Case " << i << ": Triple pangram!!!" << "\n";
                break;
            default:
                cout << "Case " << i << ": Not a pangram" << "\n";
                break;
        }
    }

    return 0;
}

```