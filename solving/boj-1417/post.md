[문제 바로가기](https://boj.kr/1417)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> vote;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        vote.push_back(input);
    }

    int ans = 0;
    while(true){
        int max_idx = 0;
        int max_val = 0;
        for(int i = 1; i < N; i++){
            if(vote[i] > max_val){
                max_idx = i;
                max_val = vote[i];
            }
        }

        if(max_val < vote[0]){
            break;
        }

        ans++;
        vote[0]++;
        vote[max_idx]--;
    }

    cout << ans << "\n";

    return 0;
}
```