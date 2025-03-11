[문제 바로가기](https://boj.kr/2485)

```c++
#include <bits/stdc++.h>

using namespace std;

int gcd(int A, int B){
    int R = A % B;

    return (R == 0 ? B : gcd(B, R));
}

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> tree;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        tree.push_back(input);
    }

    sort(tree.begin(), tree.end());

    vector<int> dist(N);
    for(int i = 0; i < N - 1; i++){
        dist[i] = tree[i + 1] - tree[i];
    }

    int num = dist[0];
    for(int i = 1; i < N - 1; i++){
        num = gcd(num, dist[i]);
    }

    int ans = 0;
    for(int i = 0; i < N - 1; i++){
        ans += (dist[i] / num) - 1;
    }

    cout << ans << "\n";

    return 0;
}```