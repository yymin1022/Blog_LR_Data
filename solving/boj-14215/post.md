[문제 바로가기](https://boj.kr/14215)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    vector<int> abc;
    for(int i = 0; i < 3; i++){
        int input;
        cin >> input;
        abc.push_back(input);
    }

    sort(abc.begin(), abc.end());

    cout << abc[0] + abc[1] + min(abc[0] + abc[1] - 1, abc[2]) << "\n";

    return 0;
}
```