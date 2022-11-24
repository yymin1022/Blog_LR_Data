[문제 바로가기](https://boj.kr/10867)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isInput[100001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N;
    cin >> N;

    int cnt = 0;
    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        if(!isInput[input + 1000]){
            arr.push_back(input);
            cnt++;
            isInput[input + 1000] = true;
        }
    }

    sort(arr.begin(), arr.end());

    for(int i = 0; i < cnt; i++){
        cout << arr[i] << " ";
    }

    return 0;
}
```