[문제 바로가기](https://boj.kr/19621)

```c++
#include <bits/stdc++.h>

using namespace std;

typedef struct {
    int from;
    int to;
    int member;
} meeting;

int N, ans;
vector<meeting> arr;
bool isUsing[26];

void func(int num){
    if(num == N){
        bool flag = true;
        int prev = -2;
        int sum = 0;

        for(int i = 0; i < N; i++){
            if(isUsing[i]){
                if(i - prev == 1){
                    flag = false;
                    break;
                }else{
                    prev = i;
                    sum += arr[i].member;
                }
            }
        }

        if(flag){
            ans = max(sum, ans);
        }
    }else{
        isUsing[num] = true;
        func(num + 1);
        isUsing[num] = false;
        func(num + 1);
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;

    for(int i = 0; i < N; i++){
        int A, B, C;
        cin >> A >> B >> C;
        arr.push_back({A, B, C});
    }

    func(0);

    cout << ans << "\n";

    return 0;
}
```