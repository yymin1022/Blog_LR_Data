[문제 바로가기](https://boj.kr/5545)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, A, B, C;
    cin >> N >> A >> B >> C;

    vector<int> arr;
    for (int i = 0; i < N; i++) {
        int D;
        cin >> D;
        arr.push_back(D);
    }

    sort(arr.begin(), arr.end(), greater<>());

    int ans = C / A;
    int totalPrice = A;
    int totalCal = C;
    for(int i = 0; i < N; i++){
        totalCal += arr[i];
        totalPrice += B;

        if(ans < totalCal / totalPrice){
            ans = totalCal / totalPrice;
        }
    }

    cout << ans << "\n";

    return 0;
}
```