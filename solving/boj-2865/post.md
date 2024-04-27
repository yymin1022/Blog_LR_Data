[문제 바로가기](https://boj.kr/2865)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M, K;
    cin >> N >> M >> K;

    map<int, double> data;
    for(int i = 0; i < M; i++){
        for(int j = 0; j < N; j++){
            int A;
            double B;
            cin >> A >> B;
            data[A] = max(B, data[A]);
        }
    }

    vector<double> arr;
    for(auto iter = data.begin(); iter != data.end(); iter++){
        arr.push_back(iter->second);
    }

    sort(arr.begin(), arr.end(), greater<double>());

    double ans = 0;
    for(int i = 0; i < K; i++){
        ans += arr[i];
    }

    cout << fixed;
    cout.precision(1);
    cout << ans << "\n";

    return 0;
}

```