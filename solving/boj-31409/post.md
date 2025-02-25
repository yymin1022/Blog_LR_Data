[문제 바로가기](https://boj.kr/31409)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    for(int i = 1; i <= N; i++){
        cin >> arr[i];

        if(arr[i] == i){
            if(i == 1){
                arr[i] = N;
            }else{
                arr[i] = 1;
            }

            ans++;
        }
    }

    cout << ans << "\n";

    for(int i = 1; i <= N; i++){
        cout << arr[i] << " ";
    }

    return 0;
}
```
