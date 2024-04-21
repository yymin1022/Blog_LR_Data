[문제 바로가기](https://boj.kr/11003)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, L;
    cin >> N >> L;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    deque<pair<int, int>> dq;
    for(int i = 0; i < N; i++){
        if(!dq.empty() && dq.front().second < i - L + 1){
            dq.pop_front();
        }

        while(!dq.empty() && dq.back().first > arr[i]){
            dq.pop_back();
        }

        dq.push_back(make_pair(arr[i], i));

        cout << dq.front().first << " ";
    }

    return 0;
}
```