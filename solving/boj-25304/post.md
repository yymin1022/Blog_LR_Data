[문제 바로가기](https://boj.kr/25304)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int X, N;
    cin >> X >> N;

    int sum = 0;
    for(int i = 0; i < N; i++){
        int a, b;
        cin >> a >> b;

        sum += a * b;
    }

    if(sum == X){
        cout << "Yes" << "\n";
    }else{
        cout << "No" << "\n";
    }

    return 0;
}```