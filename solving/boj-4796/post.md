[문제 바로가기](https://boj.kr/4796)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int cnt = 0;
    while(cnt++){
        int L, P, V;
        cin >> L >> P >> V;

        if(L == 0 && P == 0 && V == 0){
            break;
        }

        int yes = V / P;
        int no = V % P;
        if (L < no){
            no = L;
        }

        cout << "Case "<< cnt << ": " << L * yes + no << "\n";
    }

    return 0;
}
```