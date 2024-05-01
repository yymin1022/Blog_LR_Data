[문제 바로가기](https://boj.kr/12760)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> cards[101];
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            int input;
            cin >> input;
            cards[i].push_back(input);
        }

        sort(cards[i].begin(), cards[i].end(), greater<>());
    }

    vector<int> score(N, 0);
    for(int j = 0; j < M; j++){
        int winCard = 0;
        for(int i = 0; i < N; i++){
            winCard = max(cards[i][j], winCard);
        }
        for(int i = 0; i < N; i++){
            if(cards[i][j] == winCard){
                score[i]++;
            }
        }
    }

    int winCntMax = 0;
    for(int i = 0; i < N; i++){
        winCntMax = max(score[i], winCntMax);
    }

    for(int i = 0; i < N; i++){
        if(score[i] == winCntMax){
            cout << i + 1 << " ";
        }
    }

    return 0;
}
```