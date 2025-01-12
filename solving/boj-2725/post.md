[문제 바로가기](https://boj.kr/2725)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[1001];

int gcd(int a, int b) {
    int t;
    while (b) {
        t = a % b;
        a = b;
        b = t;
    }
    return a;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int C;
    cin >> C;

    arr[1] = 3;
    for(int i = 2; i <= 1000; i++){
        int cnt = 0;
        for(int j = 1; j < i; j++){
            if(gcd(i, j) == 1){
                cnt++;
            }
        }
        arr[i] = arr[i - 1] + 2 * cnt;
    }

    while(C--){
        int N;
        cin >> N;
        cout << arr[N] << "\n";
    }

    return 0;
}
```