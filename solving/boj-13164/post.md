[문제 바로가기](https://boj.kr/13164)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N, K;
    cin >> N >> K;

    int ans = 0;
    vector<int> diff;
    vector<int> student;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        student.push_back(input);

        if(i > 0){
            ans += student[i] - student[i - 1];
            diff.push_back(student[i] - student[i - 1]);
        }
    }

    sort(diff.begin(), diff.end(), greater<int>());

    for(int i = 0; i < K - 1; i++){
        ans -= diff[i];
    }

    cout << ans << "\n";

    return 0;
}
```