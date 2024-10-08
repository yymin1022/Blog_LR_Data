[문제 바로가기](https://boj.kr/28324)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<long long> V;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        V.push_back(input);
    }

    long long ans = 1;
    long long speed = 1;
    for(int i = N - 2; i >= 0; i--){
        if(speed < V[i]){
            speed++;
        }else if(speed > V[i]){
            speed = V[i];
        }

        ans += speed;
    }

    cout << ans << "\n";

    return 0;
}

```