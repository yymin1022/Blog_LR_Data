[문제 바로가기](https://boj.kr/1622)

```c++
#include <bits/stdc++.h>

using namespace std;

int cntA[26];
int cntB[26];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string A, B;
    while(getline(cin, A) && getline(cin, B)){
        memset(cntA, 0, sizeof(cntA));
        memset(cntB, 0, sizeof(cntB));

        for(int i = 0; i < A.size(); i++){
            cntA[A[i] - 'a']++;
        }
        for(int i = 0; i < B.size(); i++){
            cntB[B[i] - 'a']++;
        }

        for(int i = 0; i < 26; i++){
            int cnt = min(cntA[i], cntB[i]);

            for(int j = 0; j < cnt; j++){
                cout << (char)('a' + i);
            }
        }

        cout << "\n";
    }

    return 0;
}
```