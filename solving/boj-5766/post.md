[문제 바로가기](https://boj.kr/5766)

```c++
#include <bits/stdc++.h>

using namespace std;

bool cmp(pair<long long, string> A, pair<long long, string> B){
    if(A.first == B.first){
        return A.second < B.second;
    }
    return A.first > B.first;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    while(1){
        int N, M;
        cin >> N >> M;

        if(N == 0 && M == 0){
            break;
        }

        map<int, int> score;
        int first = 0;
        int second = 0;
        for(int i = 0; i < N * M; i++){
            int X;
            cin >> X;
            score[X]++;
        }

        for(auto iter = score.begin(); iter != score.end(); iter++){
            first = max(iter->second, first);
        }

        for(auto iter = score.begin(); iter != score.end(); iter++){
            if(iter->second != first){
                second = max(iter->second, second);
            }
        }

        for(auto iter = score.begin(); iter != score.end(); iter++){
            if(iter->second == second){
                cout << iter->first << " ";
            }
        }

        cout << "\n";
    }

    return 0;
}
```