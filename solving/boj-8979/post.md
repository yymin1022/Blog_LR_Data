[문제 바로가기](https://boj.kr/8979)

```c++
#include <bits/stdc++.h>

using namespace std;

typedef struct{
    int country;
    int gold;
    int silver;
    int bronze;
    int rank;
}medal;

bool compareMedal(const medal A, const medal B){
    if(A.gold == B.gold){
        if(A.silver == B.silver){
            if(A.bronze == B.bronze){
                return A.country < B.country;
            }
            return A.bronze > B.bronze;
        }
        return A.silver > B.silver;
    }
    return A.gold > B.gold;
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<medal> arr;
    for(int i = 0; i < N; i++){
        int c, g, s, b;
        cin >> c >> g >> s >>b;

        arr.push_back({c, g, s, b, 1});
    }

    sort(arr.begin(), arr.end(), compareMedal);

    int ansIdx;
    for(int i = 0; i < arr.size(); i++){
        if(arr[i].country == K){
            ansIdx = i;
        }
        if(i > 0 && arr[i].gold == arr[i - 1].gold && arr[i].silver == arr[i - 1].silver && arr[i].bronze == arr[i - 1].bronze){
            arr[i].rank = arr[i - 1].rank;
        }else{
            arr[i].rank = i + 1;
        }
    }

    cout << arr[ansIdx].rank << "\n";

    return 0;
}
```