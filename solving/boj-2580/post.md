[문제 바로가기](https://boj.kr/2580)

```c++
#include <bits/stdc++.h>

using namespace std;

bool check(int, int);
void dfs(int);

bool isFound = false;
int sudoku[10][10];
vector<pair<int, int>> blanks;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    for(int i = 0; i < 9; i++){
        for(int j = 0; j < 9; j++){
            cin >> sudoku[i][j];

            if(sudoku[i][j] == 0){
                blanks.push_back(make_pair(i, j));
            }
        }
    }

    dfs(0);

    for(int i = 0; i < 9; i++){
        for(int j = 0; j < 9; j++){
            cout << sudoku[i][j] << " ";
        }
        cout << "\n";
    }

    return 0;
}

bool check(int x, int y){
    int curNum = sudoku[x][y];

    for(int i = 0; i < 9; i++){
        if(sudoku[x][i] == curNum && i != y){
            return false;
        }
        if(sudoku[i][y] == curNum && i != x){
            return false;
        }
    }

    int squareX = x / 3;
    int squareY = y / 3;
    for(int i = squareX * 3; i < squareX * 3 + 3; i++){
        for(int j = squareY * 3; j < squareY * 3 + 3; j++){
            if(sudoku[i][j] == curNum){
                if(i != x && j != y){
                    return false;
                }
            }
        }
    }

    return true;
}

void dfs(int cnt){
    if(cnt == blanks.size()){
        isFound = true;
        return;
    }

    int curX = blanks[cnt].first;
    int curY = blanks[cnt].second;
    for(int i = 1; i <= 9; i++){
        sudoku[curX][curY] = i;
        if(check(curX, curY)){
            dfs(cnt + 1);
        }

        if(isFound){
            return;
        }
    }
    sudoku[curX][curY] = 0;
}```