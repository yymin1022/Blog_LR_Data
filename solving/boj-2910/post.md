[문제 바로가기](https://boj.kr/2910)

```c++
#include <bits/stdc++.h>

using namespace std;

map<int, pair<int, int>> cnt;

bool cmp(int A, int B){
    if(cnt[A].first == cnt[B].first){
        return cnt[A].second < cnt[B].second;
    }
    return cnt[A].first > cnt[B].first;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, C;
    cin >> N >> C;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
        cnt[input].first++;

        if(cnt[input].first == 1){
            cnt[input].second = i;
        }
    }

    sort(arr.begin(), arr.end(), cmp);

    for(int i = 0; i < N; i++){
        cout << arr[i] << " ";
    }

    return 0;
}
```