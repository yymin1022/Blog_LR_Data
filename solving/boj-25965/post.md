[문제 바로가기](https://boj.kr/25965)

```c++
#include <bits/stdc++.h>

using namespace std;

typedef struct {
    long long K, D, A;
} KDA;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        int M;
        cin >> M;

        vector<KDA> mission;
        for(int j = 0; j < M; j++){
            long long K, D, A;
            cin >> K >> D >> A;

            mission.push_back({K, D, A});
        }

        int cntK, cntD, cntA;
        cin >> cntK >> cntD >> cntA;

        long long sum = 0;
        for(int j = 0; j < M; j++){
            long long temp = 0;
            temp += mission[j].K * cntK;
            temp -= mission[j].D * cntD;
            temp += mission[j].A * cntA;

            if(temp > 0){
                sum += temp;
            }
        }

        cout << sum << "\n";
    }

    return 0;
}
```