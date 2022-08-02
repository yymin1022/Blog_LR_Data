[문제 바로가기](https://boj.kr/5525)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    string S;
    cin >> S;

    int cnt = 0;
    for(int i = 0; i < S.size(); i++){
        int temp = 0;
        if(S[i] == 'I'){
            while(S[i + 1]  == 'O' && S[i + 2]  == 'I'){
                i += 2;
                temp++;
                if(temp == N){
                    cnt++;
                    temp--;
                }
            }
        }
    }

    cout << cnt << "\n";

    return 0;
}```