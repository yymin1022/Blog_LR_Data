[문제 바로가기](https://boj.kr/27939)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<char> plant;
    for(int i = 0; i < N; i++){
        char input;
        cin >> input;
        plant.push_back(input);
    }

    int M, K;
    cin >> M >> K;

    for(int i = 0; i < M; i++){
        bool isAble = true;
        for(int j = 0; j < K; j++){
            int input;
            cin >> input;

            if(plant[input - 1] == 'P'){
                isAble = false;
            }
        }

        if(isAble){
            cout << "W" << "\n";
            return 0;
        }
    }

    cout << "P" << "\n";

    return 0;
}
```