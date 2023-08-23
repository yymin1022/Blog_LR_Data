[문제 바로가기](https://boj.kr/2891)

```c++
#include <bits/stdc++.h>

using namespace std;

int kayak[11];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, S, R;
    cin >> N >> S >> R;

    for(int i = 1; i <= N; i++){
        kayak[i]++;
    }

    for(int i = 0; i < S; i++){
        int input;
        cin >> input;
        kayak[input] = 0;
    }

    for(int i = 0; i < R; i++){
        int input;
        cin >> input;
        kayak[input]++;
    }

    for(int i = 1; i <= N; i++){
        if(kayak[i] == 2){
            if(kayak[i - 1] == 0){
                kayak[i - 1] = 1;
                kayak[i] = 1;
            }else if(kayak[i + 1] == 0){
                kayak[i + 1] = 1;
                kayak[i] = 1;
            }
        }
    }

    int ans = 0;
    for(int i = 1; i <= N; i++){
        if(kayak[i] == 0){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}

```