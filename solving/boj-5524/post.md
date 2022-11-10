[문제 바로가기](https://boj.kr/5524)

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
        string Si;
        cin >> Si;

        for(int j = 0; j < Si.size(); j++){
            if(Si[j] - 'a' < 0){
                cout << (char)(Si[j] + 32);
            }else{
                cout << Si[j];
            }
        }

        cout << "\n";
    }

    return 0;
}
```