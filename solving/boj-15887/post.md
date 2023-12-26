[문제 바로가기](https://boj.kr/15887)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[1001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 1; i <= N; i++){
        cin >> arr[i];
    }

    vector<pair<int, int>> ans;
    for(int i = 1; i <= N; i++){
        for(int j = 1; j < N; j++){
            if(arr[j] > arr[j + 1]){
                ans.push_back(make_pair(j, j + 1));
                swap(arr[j], arr[j + 1]);
            }
        }
    }

    cout << ans.size() << "\n";
    for(auto iter: ans){
        cout << iter.first << " ";
        cout <<  iter.second << "\n";
    }

    return 0;
}
```