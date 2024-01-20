[문제 바로가기](https://boj.kr/9626)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int M, N, U, L, R, D;
    cin >> M >> N >> U >> L >> R >> D;

    vector<string> arr;
    for(int i = 0; i < M; i++){
        string input;
        cin >> input;
        arr.push_back(input);
    }

    for(int i = 0; i < U; i++){
        for(int j = 0; j < N + L + R; j++){
            cout << ((i + j) % 2 ? "." : "#");
        }
        cout << "\n";
    }

    for(int i = U; i < U + M; i++){
        for(int j = 0; j < L; j++){
            cout << ((i + j) % 2 ? "." : "#");
        }
        cout << arr[i - U];
        for(int j = N + L; j < N + L + R; j++){
            cout << ((i + j) % 2 ? "." : "#");
        }
        cout << "\n";
    }

    for(int i = M + U; i < M + U + D; i++){
        for(int j = 0; j < N + L + R; j++){
            cout << ((i + j) % 2 ? "." : "#");
        }
        cout << "\n";
    }

    return 0;
}
```