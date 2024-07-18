[문제 바로가기](https://boj.kr/14248)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[100001];
int arr[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 1; i <= N; i++){
        cin >> arr[i];
    }

    int S;
    cin >> S;

    queue<int> bfsQ;
    bfsQ.push(S);
    isVisit[S] = true;

    int ans = 0;
    while(!bfsQ.empty()){
        int cur = bfsQ.front();
        bfsQ.pop();
        ans++;

        if(cur + arr[cur] <= N && !isVisit[cur + arr[cur]]){
            bfsQ.push(cur + arr[cur]);
            isVisit[cur + arr[cur]] = true;
        }

        if(cur - arr[cur] > 0 && !isVisit[cur - arr[cur]]){
            bfsQ.push(cur - arr[cur]);
            isVisit[cur - arr[cur]] = true;
        }
    }

    cout << ans << "\n";

    return 0;
}
```