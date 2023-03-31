[문제 바로가기](https://boj.kr/2776)

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
        cin >> N;

        map<int, bool> num;
        for(int i = 0; i < N; i++){
            int input;
            cin >> input;
            num[input] = true;
        }

        int M;
        cin >> M;
        for(int i = 0; i < M; i++){
            int input;
            cin >> input;

            if(num[input]){
                cout << 1 << "\n";
            }else{
                cout << 0 << "\n";
            };
        }
    }

    return 0;
}
```