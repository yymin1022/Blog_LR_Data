[문제 바로가기](https://boj.kr/21921)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, X;
    cin >> N >> X;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);

        if(i > 0){
            arr[i] += arr[i - 1];
        }
    }

    int cnt = 1;
    int maxSum = arr[X - 1];
    for(int i = X; i < N; i++){
        if(arr[i] - arr[i - X] == maxSum){
            cnt++;
        }

        if(arr[i] - arr[i - X] > maxSum){
            cnt = 1;
            maxSum = arr[i] - arr[i - X];
        }
    }

    if(maxSum == 0){
        cout << "SAD" << "\n";
        return 0;
    }

    cout << maxSum << "\n";
    cout << cnt << "\n";

    return 0;
}
```