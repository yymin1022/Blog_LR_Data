[문제 바로가기](https://boj.kr/24511)

```c++
#include <bits/stdc++.h>

using namespace std;

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

    deque<int> dq;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        if(arr[i] == 0){
            dq.push_front(input);
        }
    }

    int M;
    cin >> M;

    for(int i = 0; i < M; i++){
        int input;
        cin >> input;
        dq.push_back(input);

        cout << dq.front() << " ";
        dq.pop_front();
    }

    return 0;
}
```