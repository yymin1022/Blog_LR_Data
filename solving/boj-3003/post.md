[문제 바로가기](https://boj.kr/3003)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int num[6] = {1, 1, 2, 2, 2, 8};
    for(int i = 0; i < 6; i++){
        int inputNum;
        cin >> inputNum;
        cout << num[i] - inputNum << " ";
    }

    return 0;
}```