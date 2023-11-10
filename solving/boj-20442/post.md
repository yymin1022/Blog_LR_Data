[문제 바로가기](https://boj.kr/20442)

```c++
#include <bits/stdc++.h>

using namespace std;

int l_cnt[3000001];
int r_cnt[3000001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int kCnt = 0;
    string input;
    cin >> input;

    vector<int> rIdx;
    for(int i = 0; i < input.size(); i++) {
        if(input[i] == 'K') {
            kCnt++;
            continue;
        }

        rIdx.push_back(i);
        l_cnt[i] = kCnt;
    }

    kCnt = 0;
    for(int i = input.size() - 1; i >= 0; i--) {
        if(input[i] == 'K') {
            kCnt++;
            continue;
        }

        r_cnt[i] = kCnt;
    }

    int left = 0;
    int right = rIdx.size() - 1;
    int result = 0;
    while(left <= right) {
        int kCnt1 = l_cnt[rIdx[left]];
        int kCnt2 = r_cnt[rIdx[right]];

        result = max(result, right - left + 1 + (min(kCnt1, kCnt2) * 2));

        if(kCnt1 > kCnt2) {
            right--;
        }else{
            left++;
        }
    }

    cout << result;

    return 0;
}
```