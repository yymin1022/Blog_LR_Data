[문제 바로가기](https://boj.kr/1326)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[10001];
int arr[10001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 1; i <= N; i++){
        cin >> arr[i];
    }

    int L, R;
    cin >> L >> R;

    queue<pair<int, int>> bfsQ;
    bfsQ.push(make_pair(L, 0));
    isVisit[L] = true;
    while(!bfsQ.empty()){
        int cur = bfsQ.front().first;
        int cnt = bfsQ.front().second;
        bfsQ.pop();

        if(cur == R){
            cout << cnt << "\n";
            return 0;
        }

        for(int i = arr[cur]; cur + i <= N; i += arr[cur]){
            if(!isVisit[cur + i]){
                bfsQ.push(make_pair(cur + i, cnt + 1));
                isVisit[cur + i] = true;
            }
        }

        for(int i = arr[cur]; cur - i >= 1; i += arr[cur]){
            if(!isVisit[cur - i]){
                bfsQ.push(make_pair(cur - i, cnt + 1));
                isVisit[cur - i] = true;
            }
        }
    }

    cout << -1 << "\n";

    return 0;
}
```