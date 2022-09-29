[문제 바로가기](https://boj.kr/2161)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    queue<int> Q;
    for(int i = 1; i <= N; i++){
        Q.push(i);
    }

    int i = 0;
    while(!Q.empty()){
        if(i % 2){
            Q.push(Q.front());
        }else{
            cout << Q.front() << " ";
        }
        Q.pop();
        i++;
    }

    return 0;
}
```