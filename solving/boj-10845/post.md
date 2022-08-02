[문제 바로가기](https://boj.kr/10845)

```c++
#include <iostream>
#include <queue>
#include <string>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int num;
    cin >> num;

    queue<int> numQueue;

    for(int i = 0; i < num; i++){
        string command;
        cin >> command;

        if(command == "push"){
            int input;
            cin >> input;

            numQueue.push(input);
        }else if(command == "pop"){
            if(!numQueue.empty()){
                cout << numQueue.front() << "\n";
                numQueue.pop();
            }else{
                cout << -1 << "\n";
            }
        }else if(command == "size"){
            cout << numQueue.size() << "\n";
        }else if(command == "empty"){
            cout << (int)numQueue.empty() << "\n";
        }else if(command == "front"){
            if(!numQueue.empty()){
                cout << numQueue.front() << "\n";
            }else{
                cout << -1 << "\n";
            }
        }else if(command == "back"){
            if(!numQueue.empty()){
                cout << numQueue.back() << "\n";
            }else{
                cout << -1 << "\n";
            }
        }
    }

    return 0;
}```