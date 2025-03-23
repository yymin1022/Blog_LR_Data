[문제 바로가기](https://boj.kr/16499)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    set<string> group;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        sort(input.begin(), input.end());
        group.insert(input);
    }

    cout << group.size() << "\n";

    return 0;
}
```