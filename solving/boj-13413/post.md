[문제 바로가기](https://boj.kr/13413)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        string A, B;
        cin >> N >> A >> B;

        int cntB = 0;
        int cntW = 0;
        for(int i = 0; i < N; i++){
            if(A[i] != B[i]){
                if(A[i] == 'B'){
                    cntB++;
                }else{
                    cntW++;
                }
            }
        }

        cout << (cntB < cntW ? cntW : cntB) << "\n";
    }

    return 0;
}
```