[문제 바로가기](https://boj.kr/22942)

```c++
#include <bits/stdc++.h>

using namespace std;

typedef struct{
    int x;
    bool isLeft;
    int idx;
}circle;

bool cmp(circle A, circle B){
    return A.x < B.x;
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<circle> arr;
    for(int i = 0; i < N; i++){
        int x, r;
        cin >> x >> r;
        arr.push_back({x - r, true, i});
        arr.push_back({x + r, false, i});
    }

    sort(arr.begin(), arr.end(), cmp);

    stack<int> stk;
    for(int i = 0; i < N; i++){
        if(arr[i].isLeft){
            stk.push(arr[i].idx);
        }else{
            if(arr[i].idx == stk.top()){
                stk.pop();
            }else{
                cout << "NO" << "\n";
                return 0;
            }
        }
    }

    cout << "YES" << "\n";

    return 0;
}
```