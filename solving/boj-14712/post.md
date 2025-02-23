[문제 바로가기](https://boj.kr/14712)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[26][26];
int R, C, ans;
void dfs(int r, int c){
    if(r > R){
        ans++;
        return;
    }

    if(c < C){
        dfs(r, c + 1);
    }else{
        dfs(r + 1, 1);
    }

    if(!(arr[r - 1][c - 1] && arr[r - 1][c] && arr[r][c - 1])){
        arr[r][c] = 1;

        if(c < C){
            dfs(r, c + 1);
        }else{
            dfs(r + 1, 1);
        }

        arr[r][c] = 0;
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> R >> C;

    dfs(1, 1);

    cout << ans << "\n";

    return 0;
}
```