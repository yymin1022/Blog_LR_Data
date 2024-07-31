[문제 바로가기](https://boj.kr/6032)

```c++
#include <bits/stdc++.h>

using namespace std;

typedef struct {
    long long joy;
    long long price;
    int idx;
} toy;

bool cmp(toy A, toy B){
    return A.joy * B.price > A.price * B.joy;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<toy> arr;
    for(int i = 1; i <= N; i++){
        long long A, B;
        cin >> A >> B;
        arr.push_back({A, B, i});
    }

    sort(arr.begin(), arr.end(), cmp);

    cout << arr[0].price + arr[1].price + arr[2].price << "\n";

    for(int i = 0; i < 3; i++){
        cout << arr[i].idx << "\n";
    }

    return 0;
}
```