[문제 바로가기](https://boj.kr/28292)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

	if(N < 3){
        cout << 1 << "\n";;
    }else if(N < 6){
        cout << 2 << "\n";
    }else{
        cout << 3 << "\n";
    }

    return 0;
}
```