[문제 바로가기](https://boj.kr/2668)

```c++
#include <bits/stdc++.h>

using namespace std;

int N, ans;
int arr[101];
bool isVisit[101];

void dfs(int num, int idx){
    for(int i = 1; i <= N; i++){
        if(num == idx){
            ans++;
            isVisit[num] = true;
            return;
        }
        num = arr[num];
    }
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    cin >> N;

    for(int i = 1; i <= N; i++){
        cin >> arr[i];
    }

    for(int i = 1; i <= N; i++){
        dfs(arr[i], i);
    }

    cout << ans << "\n";

    for(int i = 1; i <= N; i++){
        if(isVisit[i]){
            cout << i << "\n";
        }
    }

    return 0;
}
```