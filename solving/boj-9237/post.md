[문제 바로가기](https://boj.kr/9237)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> tree;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        tree.push_back(input);
    }

    sort(tree.begin(), tree.end(), greater<int>());

    int ans = 0;
    for(int i = 0; i < N; i++){
        tree[i] += i + 1;
        ans = max(tree[i], ans);
    }

    cout << ans + 1 << "\n";

    return 0;
}
```