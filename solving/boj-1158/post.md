[문제 바로가기](https://boj.kr/1158)

```c++
#include <iostream>
#include <queue>

using namespace std;

int main(){
    int N, K;
    
    cin >> N >> K;
    
    queue<int> q;
    for(int i = 0; i < N; i++){
        q.push(i + 1);
    }

    cout << "<";

    while(true){
        for(int i = 1; i < K; i++){
            q.push(q.front());
            q.pop();
        }

        cout << q.front();

        q.pop();

        if(q.empty()){
            break;
        }else{
            cout << ", ";
        }
    }

    cout << ">";

    return 0;
}```