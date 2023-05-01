[문제 바로가기](https://boj.kr/1388)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool isVisit[51][51];
char room[51][51];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < N; i++){
        string S;
        cin >> S;
        for(int j = 0; j < S.size(); j++){
            room[i][j] = S[j];
        }
    }

    int cnt = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            if(isVisit[i][j]){
                continue;
            }

            cnt++;
            
            int k = 0;
            if(room[i][j] == '-'){
                while(j + k < M && room[i][j + k] == '-'){
                    isVisit[i][j + k] = true;
                    k++;
                }
            }
            if(room[i][j] == '|'){
                while(i + k < N && room[i + k][j] == '|'){
                    isVisit[i + k][j] = true;
                    k++;
                }
            }
        }
    }

    cout << cnt << "\n";

    return 0;
}
```