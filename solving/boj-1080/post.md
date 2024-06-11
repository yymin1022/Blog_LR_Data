[문제 바로가기](https://boj.kr/1080)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr1[51][51];
int arr2[51][51];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        for(int j = 0; j < M; j++){
            arr1[i][j] = input[j] - '0';
        }
    }

    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        for(int j = 0; j < M; j++){
            arr2[i][j] = input[j] - '0';
        }
    }

    int ans = 0;
    for(int i = 0; i < N - 2; i++){
        for(int j = 0; j < M - 2; j++){
            if(arr1[i][j] != arr2[i][j]){
                ans++;
                for(int x = i; x < i + 3; x++){
                    for(int y = j; y < j + 3; y++){
                        arr1[x][y] = (arr1[x][y] == 0 ? 1 : 0);
                    }
                }
            }
        }
    }

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            if(arr1[i][j] != arr2[i][j]){
                cout << -1 << "\n";
                return 0;
            }
        }
    }

    cout << ans << "\n";

    return 0;
}

```
