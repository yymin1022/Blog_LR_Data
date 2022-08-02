[문제 바로가기](https://boj.kr/16139)

```c++
#include <bits/stdc++.h>

using namespace std;

int cnt[200001][27];
 
int main(void) {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int q;
    string word;
    cin >> word >> q;

    for(int i = 0; i < word.size(); i++){
        for(int j = 0; j < 26; j++){
            if(i == 0){
                cnt[i][j] = 0;
            }else{
                cnt[i][j] = cnt[i - 1][j];
            }
        }
        cnt[i][word[i] - 'a']++;
    }

    for(int i = 0; i < q; i++){
        char input;
        int l, r;
        cin >> input >> l >> r;

        if(l == 0){
            cout << cnt[r][input - 'a'] << "\n";
        }else{
            cout << cnt[r][input - 'a'] - cnt[l - 1][input - 'a'] << "\n";
        }
    }

    return 0;
}```