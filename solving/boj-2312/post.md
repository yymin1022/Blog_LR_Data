[문제 바로가기](https://boj.kr/2312)

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
        int N;
        cin >> N;

        if(N % 2 == 0){
            int num = 0;
            while(N % 2 == 0){
                N /= 2;
                num++;
            }
            cout << 2 << " ";
            cout << num << "\n";
        }

        for(int i = 3; i * i <= N; i += 2){
            if(N % i == 0){
                int num = 0;
                while(N % i == 0){
                    N /= i;
                    num++;
                }

                cout << i << " ";
                cout << num << "\n";
            }
        }

        if(N > 1){
            cout << N << " ";
            cout << 1 << "\n";
        }
    }

    return 0;
}
```