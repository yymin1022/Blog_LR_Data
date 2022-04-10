[문제 바로가기](https://boj.kr/1966)

```c++
#include <iostream>
#include <queue>
#include <utility>

using namespace std;

int getMaxQ();

queue<pair<int, int>> printQ;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int num;
    cin >> num;

    for(int i = 0; i < num; i++){
        int N, M;
        cin >> N >> M;

        printQ = queue<pair<int, int>>();

        for(int j = 0; j < N; j++){
            int input;
            cin >> input;
            printQ.push(make_pair(j, input));
        }

        int count = 1;
        while(!printQ.empty()){
            int maxPrior = getMaxQ();
    
            if(printQ.front().second == maxPrior){
                if(printQ.front().first == M){
                    cout << count << "\n";
                    break;
                }
                printQ.pop();
                count++;
            }else{
                printQ.push(printQ.front());
                printQ.pop();
            }
        }
    }

    return 0;
}

int getMaxQ(){
    int maxValue = -1;

    for(int i = 0; i < printQ.size(); i++){
        if(printQ.front().second > maxValue){
            maxValue = printQ.front().second;
        }

        printQ.push(printQ.front());
        printQ.pop();
    }

    return maxValue;
}
```