[문제 바로가기](https://boj.kr/14405)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    string tmp;
    for(int i = 0; i < S.length(); i++){
        tmp.push_back(S[i]);

        if(tmp == "pi" || tmp == "ka" || tmp == "chu"){
            tmp.clear();
        }
    }

    cout << (tmp.empty() ? "YES" : "NO") << "\n";

    return 0;
}
```