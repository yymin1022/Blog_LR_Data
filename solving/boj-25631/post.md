[문제 바로가기](https://boj.kr/25631)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    for(int i = 0; i < N - 1; i++){
        for(int j = i + 1; j < N; j++){
            if(arr[i] < arr[j] && !isVisit[j]){
                arr[i] = 0;
                isVisit[j] = true;
                break;
            }
        }
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        if(arr[i]){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```