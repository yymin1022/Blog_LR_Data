[문제 바로가기](https://boj.kr/30804)

```c++
#include  <bits/stdc++.h>

using namespace std;

int num[200001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    int ans = 0;
    int cnt = 0;
    int left = 0;
    int right = 0;
    int tmp = 0;
    while(right < N){
        if(num[arr[right]] == 0){
            cnt++;
        }

        num[arr[right]]++;
        right++;
        tmp++;

        if(cnt > 2){
            num[arr[left]]--;
            if(num[arr[left]] == 0){
                cnt--;
            }
            left++;
            tmp--;
        }

        ans = max(tmp, ans);
    }

    cout << ans << "\n";

    return 0;
}
```
