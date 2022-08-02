[문제 바로가기](https://boj.kr/7785)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int N;
    cin >> N;

    map<string, bool> person;
    for(int i = 0; i < N; i++){
        string name, cmd;
        cin >> name >> cmd;

        if(cmd == "enter"){
            person[name] = true;
        }else{
            person[name] = false;
        }
    }

    for(auto iter = person.rbegin(); iter != person.rend(); iter++){
        if(iter->second){
            cout << iter->first << "\n";
        }
    }

    return 0;
}```