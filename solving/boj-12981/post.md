[문제 바로가기](https://boj.kr/12981)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    vector<int> ball;
    for(int i = 0; i < 3; i++){
        int input;
        cin >> input;
        ball.push_back(input);
    }

    sort(ball.begin(), ball.end());

    int ans = ball[0];
    ball[1] -= ball[0];
    ball[2] -= ball[0];

    ans += ball[1] / 3 + ball[2] / 3;

    if(ball[1] % 3 != 0){
        ans++;
    }

    if(ball[2] % 3 != 0){
        ans++;
    }

    if(ball[1] % 3 == 1 && ball[2] % 3 == 1){
        ans--;
    }

    cout << ans << "\n";

    return 0;
}

```