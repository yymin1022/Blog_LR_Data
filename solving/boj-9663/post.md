[문제 바로가기](https://boj.kr/9663)

```c++
#include <bits/stdc++.h>

using namespace std;

bool ver[16], diag1[25], diag2[25];
int N, cnt;

void search(int idx){
    if(idx == N){
        cnt++;
        return;
    }

    for(int i = 0; i < N; i++){
        if(!ver[i] && !diag1[i + idx] && !diag2[i - idx + N]){
            ver[i] = true;
            diag1[i + idx] = true;
            diag2[i - idx + N] = true;
            search(idx + 1);
            ver[i] = false;
            diag1[i + idx] = false;
            diag2[i - idx + N] = false;
        }
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;

    search(0);

    cout << cnt << "\n";

    return 0;
}```