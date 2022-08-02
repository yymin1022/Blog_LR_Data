[문제 바로가기](https://boj.kr/10250)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    int T;
    cin >> T;

    for(int i = 0; i < T; i++){
        int H, W, N;
        cin >> H >> W >> N;

        int x, y;

        if(N % H){
            x = N / H + 1;
            y = N % H;
        }else{
            x = N / H;
            y = H;
        }
        
        cout << y * 100 + x << "\n";
    }
}```