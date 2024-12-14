[문제 바로가기](https://boj.kr/31845)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    deque<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end(), greater<>());

    int ans = 0;
    while(M--){
        if(arr.front() > 0){
            ans += arr.front();
            arr.pop_front();

            if(!arr.empty()){
                arr.pop_back();
            }
        }else{
            break;
        }

        if(arr.empty()){
            break;
        }
    }

    cout << ans << "\n";

    return 0;
}
```
