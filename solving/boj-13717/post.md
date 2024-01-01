[문제 바로가기](https://boj.kr/13717)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ansCnt = 0;
    int maxCnt = 0;
    string ansName;
    for(int i = 0; i < N; i++){
        string P;
        int K, M;
        cin >> P >> K >> M;

        int cnt = 0;
        while(K <= M){
            M -= K;
            M += 2;
            ansCnt++;
            cnt++;
        }

        if(maxCnt < cnt){
            ansName =  P;
            maxCnt = cnt;
        }
    }

    cout << ansCnt << "\n";
    cout << ansName << "\n";

    return 0;
}
```