[문제 바로가기](https://boj.kr/12738)

```c++
#include  <bits/stdc++.h>

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

    vector<int> ans;
    for(int i = 0; i < N; i++){
        if(ans.size() == 0 || ans.back() < arr[i]){
            ans.push_back(arr[i]);
        }else{
            int idx = lower_bound(ans.begin(), ans.end(), arr[i]) - ans.begin();
            ans[idx] = arr[i];
        }
    }

    cout << ans.size() << "\n";

    return 0;
}
```