[문제 바로가기](https://boj.kr/1706)

```c++
#include  <bits/stdc++.h>

using namespace std;

char board[21][21];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int R, C;
    cin >> R >> C;

    vector<pair<int, int>> block;
    for(int i = 0; i < R; i++){
        string input;
        cin >> input;

        for(int j = 0; j < C; j++){
            board[i][j] = input[j];

            if(board[i][j] == '#'){
                block.push_back(make_pair(i, j));
            }
        }
    }

    vector<string> arr;
    for(int i = 0; i < R; i++){
        string tmp;
        for(int j = 0; j < C && board[i][j] != '#'; j++){
            tmp += board[i][j];
        }
        if(tmp.size() > 1){
            arr.push_back(tmp);
        }
    }

    for(int i = 0; i < C; i++){
        string tmp;
        for(int j = 0; j < R && board[j][i] != '#'; j++){
            tmp += board[j][i];
        }
        if(tmp.size() > 1){
            arr.push_back(tmp);
        }
    }

    for(int k = 0; k < block.size(); k++){
        string tmp;
        for(int j = block[k].second + 1; j < C && board[block[k].first][j] != '#'; j++){
            tmp += board[block[k].first][j];
        }
        if(tmp.size() > 1){
            arr.push_back(tmp);
        }

        tmp.clear();
        for(int j =  block[k].first + 1; j < R && board[j][block[k].second] != '#'; j++){
            tmp += board[j][block[k].second];
        }
        if(tmp.size() > 1){
            arr.push_back(tmp);
        }
    }

    sort(arr.begin(), arr.end());

    cout << arr[0] << "\n";

    return 0;
}
```