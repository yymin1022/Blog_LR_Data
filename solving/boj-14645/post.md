[문제 바로가기](https://boj.kr/14645)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    for(int i = 0; i < N; i++){
        int A, B;
        cin >> A >> B;
        K += A;
        K -= B;
    }

    cout << "비와이" << "\n";

    return 0;
}```