[문제 바로가기](https://boj.kr/23235)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S;
    getline(cin, S);

    int N = 0;
    while(S != "0"){
        N++;
        getline(cin, S);
    }

    for(int i = 1; i <= N; i++){
        cout << "Case " << i << ": Sorting... done!" << "\n";
    }

    return 0;
}```