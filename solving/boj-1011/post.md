[문제 바로가기](https://boj.kr/1011)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int i = 0; i < T; i++){
        int X, Y;
        cin >> X >> Y;

        long long temp = 0;
        while(1){
            if(temp * temp >= Y - X){
                cout << temp * 2 - 1 << "\n";
                break;
            }
            if(temp * temp + temp >= Y - X){
                cout << temp * 2 << "\n";
                break;
            }

            temp++;
        }
    }

    return 0;
}```