[문제 바로가기](https://boj.kr/2231)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        int result = i;
        int temp = i;

        while(temp != 0){
            result += temp % 10;
            temp /= 10;
        }

        if(result == N){
            cout << i << "\n";
            return 0;
        }
    }

    cout << 0 << "\n";

    return 0;
}```