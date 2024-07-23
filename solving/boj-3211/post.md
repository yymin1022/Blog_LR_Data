[문제 바로가기](https://boj.kr/3211)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> friends;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        friends.push_back(input);
    }

    sort(friends.begin(), friends.end());

    int ans = 1;
    while(ans <= N && ans < friends[ans - 1] + 1){
        ans = friends[ans - 1] + 1;
    }

    cout << ans << "\n";

    return 0;
}
```