[문제 바로가기](https://boj.kr/1451)

```c++
#include <bits/stdc++.h>

using namespace std;

int getSum(int, int, int, int);

int board[51][51];
int N, M;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        for(int j = 0; j < M; j++){
            board[i][j] = input[j] - '0';
        }
    }

    long long answer = 0;
    for(int i = 0; i < N - 2; i++){
        for(int j = i + 1; j < N - 1; j++){
            long long rec1 = getSum(0, 0, i + 1, M);
            long long rec2 = getSum(i + 1, 0, j + 1, M);
            long long rec3 = getSum(j + 1, 0, N, M);
            answer = max(rec1 * rec2 * rec3, answer);
        }
    }

    for(int i = 0; i < M - 1; i++){
        for(int j = 0; j < N - 1; j++){
            long long rec1 = getSum(0, 0, j + 1, i + 1);
            long long rec2 = getSum(j + 1, 0, N, i + 1);
            long long rec3 = getSum(0, i + 1, N, M);
            answer = max(rec1 * rec2 * rec3, answer);
        }
    }

    for(int i = 0; i < M - 1; i++){
        for(int j = 0; j < N - 1; j++){
            long long rec1 = getSum(0, 0, N, i + 1);
            long long rec2 = getSum(0, i + 1, j + 1, M);
            long long rec3 = getSum(j + 1, i + 1, N, M);
            answer = max(rec1 * rec2 * rec3, answer);
        }
    }

    for(int i = 0; i < M - 2; i++){
        for(int j = i + 1; j < M - 1; j++){
            long long rec1 = getSum(0, 0, N, i + 1);
            long long rec2 = getSum(0, i + 1, N, j + 1);
            long long rec3 = getSum(0, j + 1, N, M);
            answer = max(rec1 * rec2 * rec3, answer);
        }
    }

    for (int i = 0; i < N - 1; i++) {
        for (int j = 0; j < M - 1; j++) {
            long long rec1 = getSum(0, 0, i + 1, j + 1);
            long long rec2 = getSum(0, j + 1, i + 1, M);
            long long rec3 = getSum(i + 1, 0, N, M);
            answer = max(rec1 * rec2 * rec3, answer);
        }
    }

    for (int i = 0; i < N - 1; i++) {
        for (int j = 0; j < M - 1; j++) {
            long long rec1 = getSum(0, 0, i + 1, M);
            long long rec2 = getSum(i + 1, 0, N, j + 1);
            long long rec3 = getSum(i + 1, j + 1, N, M);
            answer = max(rec1 * rec2 * rec3, answer);
        }
    }

    cout << answer << "\n";

    return 0;
}

int getSum(int x1, int y1, int x2, int y2){
    int sum = 0;
    for(int i = x1; i < x2; i++){
        for(int j = y1; j < y2; j++){
            sum += board[i][j];
        }
    }

    return sum;
}```