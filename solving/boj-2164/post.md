[문제 바로가기](https://boj.kr/2164)

```c++
#include <iostream>
#include <queue>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int num;
    cin >> num;

    queue<int> numQueue;

    for(int i = 0; i < num; i++){
        numQueue.push(i + 1);
    }

    while(1){
        if(numQueue.size() > 1){
            numQueue.pop();
            numQueue.push(numQueue.front());
            numQueue.pop();
        }else{
            cout << numQueue.front() << "\n";
            break;
        }
    }

    return 0;
}
```