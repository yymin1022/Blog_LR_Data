[문제 바로가기](https://boj.kr/11729)

```c++
#include <bits/stdc++.h>

using namespace std;

void hanoii(int, int, int);

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    cout << (int)pow(2, N) - 1 << "\n";
    hanoii(N, 1, 3);

    return 0;
}

void hanoii(int n, int from, int to){
    if(n == 0){
        return;
    }else{
        hanoii(n - 1, from, 6 - from - to);
        cout << from << " " << to << "\n";
        hanoii(n - 1, 6 - from - to, to);
    }
}
```