[문제 바로가기](https://boj.kr/14646)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool arr[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    int cnt = 0;
    for(int i = 0; i < N * 2; i++){
        int input;
        cin >> input;

        if(arr[input] == 0){
            arr[input] = true;
            cnt++;
        }else{
            cnt--;
        }
        ans = max(cnt, ans);
    }

    cout << ans << "\n";

    return 0;
}
```
