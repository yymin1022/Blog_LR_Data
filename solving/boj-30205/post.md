[문제 바로가기](https://boj.kr/30205)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long N, M, P;
    cin >> N >> M >> P;

    for(int i = 0; i < N; i++){
        int item = 0;
        vector<long long> power;
        for(int j = 0; j < M; j++){
            long long input;
            cin >> input;

            if(input == -1){
                item++;
            }else{
                power.push_back(input);
            }
        }

        sort(power.begin(), power.end());

        for(int j = 0; j < power.size(); j++){
            if(power[j] <= P){
                P += power[j];
            }else{
                while(item > 0 && P < power[j]){
                    item--;
                    P *= 2;
                }

                if(power[j] <= P){
                    P += power[j];
                }else{
                    cout << 0 << "\n";
                    return 0;
                }
            }
        }

        while(item > 0){
            item--;
            P *= 2;
        }
    }

    cout << 1 << "\n";

    return 0;
}
```
