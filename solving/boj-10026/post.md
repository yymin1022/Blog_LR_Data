[문제 바로가기](https://boj.kr/10026)

```c++
#include <bits/stdc++.h>

using namespace std;

void checkBlind(int, int, char);
void checkNormal(int, int, char);

int N;
int cnt;
bool isNewArea;
bool isVisit[101][101];
char paper[101][101];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;

    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        for(int j = 0; j < input.size(); j++){
            paper[i][j] = input[j];
        }
    }

    cnt = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            isNewArea = false;
            checkNormal(i, j, 'R');
            if(isNewArea) cnt++;
            isNewArea = false;
            checkNormal(i, j, 'G');
            if(isNewArea) cnt++;
            isNewArea = false;
            checkNormal(i, j, 'B');
            if(isNewArea) cnt++;
        }
    }

    cout << cnt << " ";

    memset(isVisit, false, sizeof(isVisit[0]) * 101);
    cnt = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            isNewArea = false;
            checkBlind(i, j, 'R');
            if(isNewArea) cnt++;
            isNewArea = false;
            checkBlind(i, j, 'B');
            if(isNewArea) cnt++;
        }
    }
    cout << cnt << "\n";

    return 0;
}

void checkBlind(int x, int y, char current){
    if(isVisit[x][y] || x < 0 || x >= N || y < 0 || y >= N){
        return;
    }

    if(current == 'B' && paper[x][y] == current){
        isNewArea = true;
        isVisit[x][y] = true;

        checkBlind(x - 1, y, current);
        checkBlind(x + 1, y, current);
        checkBlind(x, y - 1, current);
        checkBlind(x, y + 1, current);
    }else if(current != 'B' && paper[x][y] != 'B'){
        isNewArea = true;
        isVisit[x][y] = true;

        checkBlind(x - 1, y, current);
        checkBlind(x + 1, y, current);
        checkBlind(x, y - 1, current);
        checkBlind(x, y + 1, current);
    }
}

void checkNormal(int x, int y, char current){
    if(isVisit[x][y] || x < 0 || x >= N || y < 0 || y >= N){
        return;
    }

    if(paper[x][y] == current){
        isNewArea = true;
        isVisit[x][y] = true;

        checkNormal(x - 1, y, current);
        checkNormal(x + 1, y, current);
        checkNormal(x, y - 1, current);
        checkNormal(x, y + 1, current);
    }
}
```