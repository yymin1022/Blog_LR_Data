[문제 바로가기](https://boj.kr/17266)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> light;
    for(int i = 0; i < M; i++){
        int input;
        cin >> input;
        light.push_back(input);
    }

    int ans = 987654321;
    int fromL = 0;
    int fromR = N;
    while(fromL <= fromR){
        int mid = (fromL + fromR) / 2;

        bool flag = true;
        if(light[0] > mid)
            flag = false;
        for(int i = 0; i < M - 1; i++){
            if(light[i + 1] - light[i] > mid * 2){
                flag = false;
                break;
            }
        }

        if(N - light[M - 1] > mid){
            flag = false;
        }

        if(!flag){
            fromL = mid + 1;
        }else{
            ans = min(mid, ans);
            fromR = mid - 1;
        }
    }

    cout << ans << "\n";

    return 0;
}
```