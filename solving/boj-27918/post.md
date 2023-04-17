[문제 바로가기](https://boj.kr/27918)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int D = 0;
    int P = 0;
    for(int i = 0; i < N; i++){
        char c;
        cin >> c;

        if(c == 'D'){
            D++;
        }else{
            P++;
        }

        if(abs(D - P) >= 2){
            break;
        }
    }

    cout << D << ":" << P << "\n";

    return 0;
}
```