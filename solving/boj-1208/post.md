[문제 바로가기](https://boj.kr/1208)

```c++
#include  <bits/stdc++.h>

using namespace std;

int arr[41];
int N, S;
long long ans;
vector<int> A;
vector<int> B;

void arrA(int idx, int sum){
    if(idx >= N / 2){
        return;
    }

    sum += arr[idx];
    if(sum == S){
        ans++;
    }

    A.push_back(sum);
    arrA(idx + 1, sum);
    arrA(idx + 1, sum - arr[idx]);
}

void arrB(int idx, int sum){
    if(idx >= N){
        return;
    }

    sum += arr[idx];
    if(sum == S){
        ans++;
    }

    B.push_back(sum);
    arrB(idx + 1, sum);
    arrB(idx + 1, sum - arr[idx]);
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> S;

    for(int i = 0; i < N; i++){
        cin >> arr[i];
    }

    arrA(0, 0);
    arrB(N / 2, 0);

    sort(A.begin(), A.end());
    sort(B.begin(), B.end());

    for(int i = 0; i < A.size(); i++){
        int tmp = S - A[i];
        int from = lower_bound(B.begin(), B.end(), tmp) - B.begin();
        int to = upper_bound(B.begin(), B.end(), tmp) - B.begin();
        ans += to - from;
    }

    cout << ans << "\n";

    return 0;
}
```