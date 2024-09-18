[문제 바로가기](https://boj.kr/6752)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T, C;
    cin >> T >> C;

    vector<int> task;
    for(int i = 0; i < C; i++){
        int input;
        cin >> input;
        task.push_back(input);
    }

    sort(task.begin(), task.end());

    int cnt = 0;
    int sum = 0;
    for(int i = 0; i < C; i++){
        if(task[i] <= T - sum){
            cnt++;
            sum += task[i];
        }else{
            break;
        }
    }

    cout << cnt << "\n";

    return 0;
}
```