[문제 바로가기](https://boj.kr/28062)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int minOdd = 2147483647;
    int sum = 0;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        if(input % 2){
            minOdd = min(input, minOdd);
        }

        sum += input;
    }

    if(sum % 2) {
        sum -= minOdd;
    }
        
    cout << sum << "\n";

    return 0;
}
```