[문제 바로가기](https://boj.kr/9184)

```c++
#include <bits/stdc++.h>

using namespace std;

int w(int, int, int);

bool isVisit[51][51][51];
int dp[51][51][51];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int a, b, c;
    cin >> a >> b >> c;

    while(!(a == -1 && b == -1 && c == -1)){
        for(int i = 0; i < 51; i++){
            for(int j = 0; j < 51; j++){
                for(int k = 0; k < 51; k++){
                    dp[i][j][k] = 0;
                    isVisit[i][j][k] = false;
                }
            }
        }
        
        cout << "w(" << a << ", " << b << ", " << c << ") = " << w(a, b, c) << "\n";
        cin >> a >> b >> c;
    }

    return 0;
}

int w(int a, int b, int c){
    if(a <= 0 || b <= 0 || c <= 0){
        return 1;
    }else if(a > 20 || b > 20 || c > 20){
        return w(20, 20, 20);
    }
    
    if(isVisit[a][b][c]){
        return dp[a][b][c];
    }
    
    if(a < b && b < c){
        isVisit[a][b][c] = true;
        return dp[a][b][c] = w(a, b, c - 1) + w(a, b - 1, c - 1) - w(a, b - 1, c);
    }else{
        isVisit[a][b][c] = true;
        return dp[a][b][c] = w(a - 1, b, c) + w(a - 1, b - 1, c) + w(a - 1, b, c - 1) - w(a - 1, b - 1, c - 1);
    }
}
```