[문제 바로가기](https://boj.kr/15828)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    queue<int> routerQ;
    int input;
    cin >> input;
    while(input != -1){
        if(input == 0){
            routerQ.pop();
        }else if(routerQ.size() < N){
            routerQ.push(input);
        }

        cin >> input;
    }

    if(routerQ.empty()){
        cout << "empty" << "\n";
    }

    while(!routerQ.empty()){
        cout << routerQ.front() << " ";
        routerQ.pop();
    }

    return 0;
}

```