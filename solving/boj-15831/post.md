[문제 바로가기](https://boj.kr/15831)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N, B, W;
    cin >> N >> B >> W;

    string stone;
    cin >> stone;

    int ans = 0;
    int cntB = 0;
    int cntW = 0;
    int left = 0;
    int right = 0;
    while(right < N){
        if(cntB <= B){
            if(stone[right] == 'W'){
                cntW++;
            }else{
                cntB++;
            }
            right++;

            if(cntW >= W && cntB <= B){
                ans = max(cntB + cntW, ans);
            }
        }else{
            if(stone[left] == 'W'){
                cntW--;
            }else{
                cntB--;
            }
            left++;
        }
    }

    cout << ans << "\n";

    return 0;
}``