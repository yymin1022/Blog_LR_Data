[문제 바로가기](https://boj.kr/1448)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<long long> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end(), greater<long long>());

    for(int i = 0; i < N - 2; i++){
        if(arr[i] < arr[i + 1] + arr[i + 2]){
            cout << arr[i] + arr[i + 1] + arr[i + 2] << "\n";
            return 0;
        }
    }

    cout << -1 << "\n";

    return 0;
}

```