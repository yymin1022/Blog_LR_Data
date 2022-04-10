[문제 바로가기](https://boj.kr/2292)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    int N;
    cin >> N;

    int count = 2;
    int i = 1;
    while(count <= N){
        count += i * 6;
        i++;
    }

    if(N == 1){
        cout << 1;
    }else{
        cout << i;
    }

    return 0;
}
```