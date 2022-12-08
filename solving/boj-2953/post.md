[문제 바로가기](https://boj.kr/2953)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int ansIdx;
    int ansScore = 0;

    for(int i = 1; i <= 5; i++){
        int temp = 0;
        for(int j = 0; j < 4; j++){
            int input;
            cin >> input;
            temp += input;
        }

        if(temp > ansScore){
            ansIdx = i;
            ansScore = temp;
        }
    }

    cout << ansIdx << " " << ansScore << "\n";

    return 0;
}
```