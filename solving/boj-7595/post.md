[문제 바로가기](https://boj.kr/7595)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    while(N){
        for(int i = 1; i <= N; i++){
            for(int j = 0; j < i; j++){
                cout << "*";
            }
            cout << "\n";
        }

        cin >> N;
    }
    
    return 0;
}
```