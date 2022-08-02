[문제 바로가기](https://boj.kr/1193)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int X;
    cin >> X;

    int count;
    int sum = 0;
    for(int i = 0; i < 10000000; i++){
        if(sum >= X){
            count = i - 1;
            break;
        }
        sum += i;
    }

    if(count % 2){
        cout << sum - X + 1 << "/" << count - sum + X << "\n";
    }else{
        cout << count - sum + X << "/" << sum - X + 1 << "\n";
    }

    return 0;
}```