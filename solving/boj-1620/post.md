[문제 바로가기](https://boj.kr/1620)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    map<string, int> byName;
    map<int, string> byNum;

    for(int i = 1; i <= N; i++){
        string name;
        cin >> name;

        byName[name] = i;
        byNum[i] = name;
    }

    for(int i = 0; i < M; i++){
        string input;
        cin >> input;

        if(input[0] - '0' >= 10){
            cout << byName[input] << "\n";
        }else{
            cout << byNum[stoi(input)] << "\n";
        }
    }

    return 0;
}
```