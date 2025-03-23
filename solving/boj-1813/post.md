[문제 바로가기](https://boj.kr/1813)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    map<int, int> cnt;
    for(int i = 0, n; i < N; i++){
        int input;
        cin >> input;
        cnt[input]++;
    }

    for(int i = 50; i >= 0; i--){
        if(cnt[i] == i){
            cout << i << "\n";
            return 0;
        }
    }

    cout << -1 << "\n";

    return 0;
}

```
