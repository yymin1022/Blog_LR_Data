[문제 바로가기](https://boj.kr/4779)

```c++
#include <bits/stdc++.h>

using namespace std;

int N;
string ans;

void recur(int start, int end){
    if(end - start == 1){
        return;
    }

    int offset = (end - start) / 3;
    for(int i = start + offset; i < end - offset; i++){
        ans[i] = ' ';
    }

    recur(start, start + offset);
    recur(end - offset, end);
}

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    while(cin >> N){
        int size = pow(3, N);

        ans.clear();
        for(int i = 0; i < size; i++){
            ans.push_back('-');
        }

        recur(0, size);
        cout << ans << "\n";
    }

    return 0;
}
```