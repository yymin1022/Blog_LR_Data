[문제 바로가기](https://boj.kr/10807)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> nums;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        nums.push_back(input);
    }

    int V;
    cin >> V;

    cout << count(nums.begin(), nums.end(), V) << "\n";

    return 0;
}```