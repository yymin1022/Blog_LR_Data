[문제 바로가기](https://boj.kr/18301)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int n1, n2, n12;
    cin >> n1 >> n2 >> n12;

    cout << (n1 + 1) * (n2 + 1) / (n12 + 1) - 1 << "\n";

    return 0;
}```