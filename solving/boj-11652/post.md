[문제 바로가기](https://boj.kr/11652)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    map<long long, int> nums;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;

        nums[input]++;
    }

    long long maxCnt = 0;
    long long maxN;
    for(auto iter : nums){
        if(iter.second > maxCnt){
            maxCnt = iter.second;
            maxN = iter.first;
        }
    }

    cout << maxN << "\n";

    return 0;
}```