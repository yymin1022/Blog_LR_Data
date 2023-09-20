[문제 바로가기](https://boj.kr/16960)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> button[2001];
    vector<int> lamp(M + 1, 0);
    for(int i = 0; i < N; i++){
        int C;
        cin >> C;

        for(int j = 0; j < C; j++){
            int input;
            cin >> input;
            button[i].push_back(input);
            lamp[input]++;
        }
    }

    for(int i = 0; i < N; i++){
        for(int j = 0; j < button[i].size(); j++){
            lamp[button[i][j]]--;
        }
        bool isAvail = true;
        for(int j = 1; j <= M; j++){
            if(!lamp[j]){
                isAvail = false;
                break;
            }
        }
        if(isAvail){
            cout << 1 << "\n";
            return 0;
        }
        for(int j = 0; j < button[i].size(); j++){
            lamp[button[i][j]]++;
        }
    }

    cout << 0 << "\n";

    return 0;
}
```