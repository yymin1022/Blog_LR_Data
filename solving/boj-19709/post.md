[문제 바로가기](https://boj.kr/19709)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> arr;
    for(int i = 0; i < M; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    int cnt = 0;
    int sum = 0;
    for(int i = 0; i < M; i++){
        if(sum + arr[i] > N){
            break;
        }

        cnt++;
        sum += arr[i];
    }

    cout << cnt << "\n";

    return 0;
}
```