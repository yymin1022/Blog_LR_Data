[문제 바로가기](https://boj.kr/17863)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string N;
    cin >> N;

    if(N.size() == 7 && N.substr(0, 3) == "555"){
        cout << "YES" << "\n";
    }else{
        cout << "NO" << "\n";
    }

    return 0;
}
```