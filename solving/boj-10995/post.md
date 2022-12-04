[문제 바로가기](https://boj.kr/10995)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        if(i % 2){
            cout << " ";
        }

        for(int j = 0; j < N; j++){
            cout << "* ";
        }

        cout << "\n";
    }

    return 0;
}
```