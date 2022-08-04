[문제 바로가기](https://boj.kr/2110)

```c++
#include <bits/stdc++.h>

using namespace std;

int N, C;
vector<int> house;

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    cin >> N >> C;

    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        house.push_back(input);
    }

    sort(house.begin(), house.end());

    int ans;
    int fromL = 0;
    int fromR = house[N - 1] - house[0];
    int mid;
    while(fromL <= fromR){
        mid = (fromL + fromR) / 2;

        int houseLast = 0;
        int houseNext = 1;
        int installed = 1;
        while(installed < C && houseNext < N){
            if(house[houseNext] >= house[houseLast] + mid){
                installed++;
                houseLast = houseNext;
                houseNext = houseLast + 1;
            }else{
                houseNext++;
            }
        }

        if(installed < C){
            fromR = mid - 1;
        }else if(installed > C){
            fromL = mid + 1;
        }else{
            ans = mid;
            fromL = mid + 1;
        }
    }

    cout << ans << "\n";

    return 0;
}
```