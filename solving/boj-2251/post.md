[문제 바로가기](https://boj.kr/2251)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[201][201][201];

typedef struct {
    int A;
    int B;
    int C;
} bottle;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int A, B, C;
    cin >> A >> B >> C;

    vector<int> ans;
    queue<bottle> bfsQ;
    bfsQ.push({0, 0, C});
    while(!bfsQ.empty()){
        int curA = bfsQ.front().A;
        int curB = bfsQ.front().B;
        int curC = bfsQ.front().C;
        bfsQ.pop();

        if(isVisit[curA][curB][curC]){
            continue;
        }

        isVisit[curA][curB][curC] = true;

        if(curA == 0){
            ans.push_back(curC);
        }

        if(curA + curB > A){
            bfsQ.push({A, curA + curB - A, curC});
        }else{
            bfsQ.push({curA + curB, 0, curC});
        }

        if(curA + curB > B){
            bfsQ.push({curA + curB - B, B, curC});
        }else{
            bfsQ.push({0, curA + curB, curC});
        }

        if(curA + curC > A){
            bfsQ.push({A, curB, curA + curC - A});
        }else{
            bfsQ.push({curA + curC, curB, 0});
        }

        if(curA + curC > C){
            bfsQ.push({curA + curB - C, curB, C});
        }else{
            bfsQ.push({0, curB, curA + curC});
        }

        if(curB + curC > B){
            bfsQ.push({curA, B, curB + curC - B});
        }else{
            bfsQ.push({curA, curB + curC, 0});
        }

        if(curB + curC > C){
            bfsQ.push({curA, curB + curC - C, C});
        }else{
            bfsQ.push({curA, 0, curB + curC});
        }
    }

    sort(ans.begin(), ans.end());

    for(int i = 0; i < ans.size(); i++){
        cout << ans[i] << " ";
    }

    return 0;
}
```