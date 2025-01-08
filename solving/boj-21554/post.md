[문제 바로가기](https://boj.kr/21554)

```c++
#include <bits/stdc++.h>

using namespace std;

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

    vector<pair<int, int>> ans;
    for(int i = 0; i < N; i++){
        if(arr[i] == i + 1){
            continue;
        }

        int idx = find(arr.begin(), arr.end(), i + 1) - arr.begin();
        ans.push_back(make_pair(i + 1, idx + 1));

        reverse(arr.begin() + i, arr.begin() + idx + 1);
    }

    cout << ans.size() << "\n";

    for(int i = 0; i < ans.size(); i++){
        cout << ans[i].first << " ";
        cout << ans[i].second << "\n";
    }

    return 0;
}
```