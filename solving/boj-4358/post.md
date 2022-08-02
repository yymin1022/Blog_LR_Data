[문제 바로가기](https://boj.kr/4358)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int cnt = 0;
    map<string, int> tree;
    string input;
    while(getline(cin, input)){
        cnt++;
        tree[input]++;
    }

    cout << fixed;
    cout.precision(4);

    for(auto iter : tree){
        cout << iter.first << " " << iter.second * 100 / (double)cnt << "\n";
    }

    return 0;
}```