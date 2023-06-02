[문제 바로가기](https://boj.kr/10546)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    map<string, int> marathon;
    for(int i = 0; i < N; i++){
        string name;
        cin >> name;
        marathon[name]++;
    }

    for(int i = 0; i < N - 1; i++){
        string name;
        cin >> name;
        marathon[name]--;
    }

    for(auto iter = marathon.begin(); iter != marathon.end(); iter++){
        if(iter->second){
            cout << iter->first << "\n";
            break;
        }
    }

    return 0;
}
```