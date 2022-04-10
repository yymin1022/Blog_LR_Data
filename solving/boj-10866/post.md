[문제 바로가기](https://boj.kr/10866)

```c++
#include <iostream>
#include <deque>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int num;
    cin >> num;

    deque<int> numDeque;

    for(int i = 0; i < num; i++){
        string command;
        cin >> command;

        if(command == "push_front"){
            int input;
            cin >> input;

            numDeque.push_front(input);
        }else if(command == "push_back"){
            int input;
            cin >> input;

            numDeque.push_back(input);
        }else if(command == "pop_front"){
            if(!numDeque.empty()){
                cout << numDeque.front() << "\n";
                numDeque.pop_front();
            }else{
                cout << -1 << "\n";
            }
        }else if(command == "pop_back"){
            if(!numDeque.empty()){
                cout << numDeque.back() << "\n";
                numDeque.pop_back();
            }else{
                cout << -1 << "\n";
            }
        }else if(command == "size"){
            cout << numDeque.size() << "\n";
        }else if(command == "empty"){
            cout << (int)numDeque.empty() << "\n";
        }else if(command == "front"){
            if(!numDeque.empty()){
                cout << numDeque.front() << "\n";
            }else{
                cout << -1 << "\n";
            }
        }else if(command == "back"){
            if(!numDeque.empty()){
                cout << numDeque.back() << "\n";
            }else{
                cout << -1 << "\n";
            }
        }
    }

    return 0;
}
```