[문제 바로가기](https://boj.kr/2508)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int R, C;
        cin >> R >> C;

        vector<string> arr(R);
        for(int i = 0; i < R; i++){
            cin >> arr[i];
        }

        int cnt = 0;
        for(int i = 0; i < R; i++){
            for(int j = 0; j < C - 2; j++){
                if(arr[i][j] == '>' && arr[i][j + 1] == 'o' && arr[i][j + 2] == '<'){
                    cnt++;
                    j += 2;
                }
            }
        }

        for(int i = 0; i < C; i++){
            for(int j = 0; j < R - 2; j++){
                if(arr[j][i] == 'v' && arr[j + 1][i] == 'o' && arr[j + 2][i] == '^'){
                    cnt++;
                    j += 2;
                }
            }
        }

        cout << cnt << "\n";
    }

    return 0;
}
```