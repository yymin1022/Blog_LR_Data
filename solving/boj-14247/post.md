[문제 바로가기](https://boj.kr/14247)

```c++
#include <bits/stdc++.h>

using namespace std;

bool cmp(pair<long long, long long> A, pair<long long, long long> B){
    return A.second < B.second;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<long long> H;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        H.push_back(input);
    }

    vector<long long> W;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        W.push_back(input);
    }

    vector<pair<long long, long long>> tree;
    for(int i = 0; i < N; i++){
        tree.push_back(make_pair(H[i], W[i]));
    }

    sort(tree.begin(), tree.end(), cmp);

    long long ans = 0;
    for(int i = 0; i < N; i++){
        ans += tree[i].first + tree[i].second * i;
    }

    cout << ans << "\n";

    return 0;
}

```