[문제 바로가기](https://boj.kr/1449)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, L;
    cin >> N >> L;

    vector<int> hole;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        hole.push_back(input);
    }

    L--;
    sort(hole.begin(), hole.end());

    int ans = 0;
    int taped = 0;
    for(int i = 0; i < hole.size(); i++){
        if(taped < hole[i]){
            ans++;
            taped = hole[i] + L;
        }
    }

    cout << ans << "\n";

    return 0;
}
```