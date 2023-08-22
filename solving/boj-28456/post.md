[문제 바로가기](https://boj.kr/28456)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[101][101];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, Q;
    cin >> N;

    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= N; j++){
            cin >> arr[i][j];
        }
    }

    cin >> Q;

    while(Q--){
        int cmd;
        cin >> cmd;

        if(cmd == 1){
            cin >> cmd;

            int tmp = arr[cmd][N];
            for(int i = N; i > 0; i--){
                arr[cmd][i + 1] = arr[cmd][i];
            }
            arr[cmd][1] = tmp;
        }else{
            int tmp[101][101];
            for(int i = 1; i <= N; i++){
                for(int j = 1; j <= N; j++){
                    tmp[j][N - i + 1] = arr[i][j];
                }
            }
            for(int i = 1; i <= N; i++){
                for(int j = 1; j <= N; j++){
                    arr[i][j] = tmp[i][j];
                }
            }
        }
    }

    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= N; j++){
            cout << arr[i][j] << " ";
        }
        cout << "\n";
    }

    return 0;
}
```
