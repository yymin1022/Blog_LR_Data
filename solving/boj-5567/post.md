[문제 바로가기](https://boj.kr/5567)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> friends[501];
    for(int i = 0; i < M; i++){
        int A, B;
        cin >> A >> B;
        friends[A].push_back(B);
        friends[B].push_back(A);
    }

    set<int> visitor;
    for(int i = 0; i < friends[1].size(); i++){
        visitor.insert(friends[1][i]);
        for(int j = 0; j < friends[friends[1][i]].size(); j++){
            visitor.insert(friends[friends[1][i]][j]);
        }
    }

    visitor.erase(1);

    cout << visitor.size() << "\n";

    return 0;
}
```