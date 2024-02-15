[문제 바로가기](https://boj.kr/18310)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> home;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        home.push_back(input);
    }

    sort(home.begin(), home.end());

    cout << home[(N - 1) / 2] << "\n";

    return 0;
}
```