[문제 바로가기](https://boj.kr/10103)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    pair<int, int> score = make_pair(100, 100);
    for(int i = 0; i < N; i++){
        int a, b;
        cin >> a >> b;

        if(a > b){
            score.second -= a;
        }else if(a < b){
            score.first -= b;
        }
    }

    cout << score.first << "\n";
    cout << score.second << "\n";

    return 0;
}
```