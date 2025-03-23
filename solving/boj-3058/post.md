[문제 바로가기](https://boj.kr/3058)

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
        int ansMin = 100;
        int ansSum = 0;
        for(int i = 0; i < 7; i++){
            int input;
            cin >> input;

            if(input % 2 == 0){
                ansSum += input;
                ansMin = min(input, ansMin);
            }
        }

        cout << ansSum << " ";
        cout << ansMin << "\n";
    }

    return 0;
}
```