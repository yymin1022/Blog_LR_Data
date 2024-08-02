[문제 바로가기](https://boj.kr/29812)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, D, M;
    string S;
    cin >> N >> S >> D >> M;

    int cntH = 0;
    int cntY = 0;
    int cntU = 0;
    int energy = 0;
    int tmp = 0;
    for(int i = 0; i < N; i++){
        if(S[i] != 'H' && S[i] != 'Y' && S[i] != 'U'){
            tmp++;
        }else{
            if(S[i] == 'H'){
                cntH++;
            }else if(S[i] == 'Y'){
                cntY++;
            }else{
                cntU++;
            }
            energy += min(D * tmp, M + D);
            tmp = 0;
        }
    }

    if(tmp > 0){
        energy += min(D * tmp, M + D);
    }
    
    if(energy == 0){
        cout << "Nalmeok" << "\n";
    }else{
        cout << energy << "\n";
    }

    int cnt = min(min(cntH, cntY), cntU);
    if(cnt == 0){
        cout << "I love HanYang University" << "\n";
    }else{
        cout << cnt << "\n";
    }

    return 0;
}

```
