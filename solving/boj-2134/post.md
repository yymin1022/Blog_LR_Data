[문제 바로가기](https://boj.kr/2134)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M, K;
    cin >> N >> M >> K;

    int beforeSum = 0;
    vector<int> before;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        before.push_back(input);
        beforeSum += input;
    }

    int afterSum = 0;
    vector<int> after;
    for(int i = 0; i < M; i++){
        int input;
        cin >> input;
        after.push_back(input);
        afterSum += input;
    }

    long long ans = 0;
    int moved = 0;
    int movable = min(afterSum, beforeSum);
    for(int i = 0; i < N; i++){
        int cur = before[i];
        if(cur + moved <= movable){
            ans += cur * (i + 1);
            moved += cur;
        }else{
            ans += (movable - moved) * (i + 1);
            break;
        }
    }

    moved = 0;
    for(int i = 0; i < M; i++){
        int cur = after[i];
        if(cur + moved <= movable){
            ans += cur * (i + 1);
            moved += cur;
        }else{
            ans += (movable - moved) * (i + 1);
            break;
        }
    }

    cout << movable << " ";
    cout << ans << "\n";

    return 0;
}
```