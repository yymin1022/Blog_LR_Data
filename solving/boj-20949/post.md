[문제 바로가기](https://boj.kr/20949)

```c++
#include <bits/stdc++.h>

using namespace std;

typedef struct{
    int N;
    int W;
    int H;
} monitor;

bool comp(monitor A, monitor B){
    int ppiA = A.W * A.W + A.H * A.H;
    int ppiB = B.W * B.W + B.H * B.H;

    if(ppiA == ppiB){
        return A.N < B.N;
    }

    return ppiA > ppiB;
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N;
    cin >> N;

    vector<monitor> arr;
    for(int i = 1; i <= N; i++){
        int W, H;
        cin >> W >> H;
        arr.push_back({i, W, H});
    }

    sort(arr.begin(), arr.end(), comp);

    for(int i = 0; i < N; i++){
        cout << arr[i].N << "\n";
    }
    
    return 0;
}
```