[문제 바로가기](https://boj.kr/2506)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int offset = 0;
    int sum = 0;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        if(input){
            offset++;
        }else{
            offset = 0;
        }

        sum += offset;
    }

    cout << sum << "\n";

    return 0;
}
}```