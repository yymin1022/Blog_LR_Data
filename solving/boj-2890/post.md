[문제 바로가기](https://boj.kr/2890)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int R, C;
    cin >> R >> C;

    vector<string> photo;
    for(int i = 0; i < R; i++){
        string input;
        cin >> input;
        reverse(input.begin(), input.end());
        photo.push_back(input);
    }

    int curRank = 1;
    vector<int> rank(10, 0);
    for(int i = 1; i < C - 1; i++){
        bool isRank = false;
        for(int j = 0; j < R; j++){
            int cur = photo[j][i] - '0';
            if(cur > 0 && cur < 10 && !rank[cur]){
                isRank = true;
                rank[cur] = curRank;
            }
        }

        if(isRank){
            curRank++;
        }
    }

    for(int i = 1; i <= 9; i++){
        cout << rank[i] << "\n";
    }

    return 0;
}
```