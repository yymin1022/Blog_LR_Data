[문제 바로가기](https://boj.kr/12789)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    queue<int> q;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        q.push(input);
    }

    int idx = 1;
    stack<int> stk;
    while(idx <= N){
        if(!q.empty() && q.front() == idx){
            idx++;
            q.pop();
        }else if(!stk.empty() && stk.top() == idx){
            idx++;
            stk.pop();
        }else if(!q.empty()){
            stk.push(q.front());
            q.pop();
        }else{
            cout << "Sad" << "\n";
            return 0;
        }
    }

    cout << "Nice" << "\n";

    return 0;
}
```