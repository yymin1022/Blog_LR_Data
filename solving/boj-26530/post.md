[문제 바로가기](https://boj.kr/26530)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        int M;
        cin >> M;

        double sum = 0;
        for(int j = 0; j < M; j++){
            string name;
            int cnt;
            double price;
            cin >> name >> cnt >> price;
            sum += cnt * price;
        }

        cout << fixed;
        cout.precision(2);
        cout << "$" << sum << "\n";
    }

    return 0;
}
```