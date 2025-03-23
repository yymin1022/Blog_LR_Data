[문제 바로가기](https://boj.kr/2141)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    long long sum = 0;
    vector<pair<long long, long long>> X(N + 1);
    for(int i = 1; i <= N; i++){
        long long A, B;
        cin >> A >> B;
        X[i] = make_pair(A, B);
        sum += B;
    }

    sort(X.begin() + 1, X.end());

    long long tmp = 0;
    for(int i = 1; i <= N; i++){
        tmp += X[i].second;
        if(tmp >= (sum + 1) / 2){
            cout << X[i].first << "\n";
            return 0;
        }
    }

    return 0;
}

```
