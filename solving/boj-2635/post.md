[문제 바로가기](https://boj.kr/2635)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> ans;
    for(int i = 1; i <= N; i++){
        vector<int> arr;
        arr.push_back(N);
        arr.push_back(i);

        int idx = 2;
        int tmp;
        while(true){
            tmp = arr[idx - 2] - arr[idx - 1];
            if(tmp < 0){
                break;
            }
            arr.push_back(tmp);
            idx++;
        }

        if(arr.size() > ans.size()){
            ans = arr;
        }
    }

    cout << ans.size() << "\n";

    for(int i = 0; i < ans.size(); i++){
        cout << ans[i] << " ";
    }

    return 0;
}
```