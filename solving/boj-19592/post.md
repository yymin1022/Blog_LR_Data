[문제 바로가기](https://boj.kr/19592)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        long long N, X, Y;
        cin >> N >> X >> Y;

        long long V = 0;
        for(int i = 1; i < N; i++){
            long long input;
            cin >> input;
            V = max(V, input);
        }

        long long lastV;
        cin >> lastV;

        if(V < lastV){
            cout << 0 << "\n";
        }else{
            bool flag = false;
            for(long long i = lastV + 1; i <= Y; i++){
                if((X - V) * lastV > (X - i) * V){
                    cout << i << "\n";
                    flag = true;
                    break;
                }
            }

            if(!flag){
                cout << -1 << "\n";
            }
        }
    }

    return 0;
}
```