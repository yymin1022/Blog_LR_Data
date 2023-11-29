[문제 바로가기](https://boj.kr/15721)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool isVisit[101][101];
int mountain[101][101];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int A, T, N;
    cin >> A >> T >> N;

    int B = 0;
    int D = 0;
    int cnt = 2;
    while(true){
        for(int i = 0; i < 4; i++){
            if(i % 2){
                D++;
            }else{
                B++;
            }

            if(B == T && N == 0){
                cout << (B + D - 1) % A << "\n";
                return 0;
            }else if(D == T && N == 1){
                cout << (B + D - 1) % A << "\n";
                return 0;
            }
        }

        for(int i = 0; i < cnt; i++){
            B++;

            if(B == T && N == 0){
                cout << (B + D - 1) % A << "\n";
                return 0;
            }
        }

        for(int i = 0; i < cnt; i++){
            D++;

            if(D == T && N == 1){
                cout << (B + D - 1) % A << "\n";
                return 0;
            }
        }
        cnt++;
    }

    return 0;
}
```