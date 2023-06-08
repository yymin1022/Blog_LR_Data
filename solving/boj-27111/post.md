[문제 바로가기](https://boj.kr/27111)

```c++
#include <iostream>
#include <string>

using namespace std;

bool arr[200001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int cnt = 0;
    for(int i = 0; i < N; i++){
        int a, b;
        cin >> a >> b;

        if(b == 0){
            if(!arr[a]){
                cnt++;
            }
            arr[a] = false;
        }else{
            if(arr[a]){
                cnt++;
            }
            arr[a] = true;
        }
    }

    for(int i = 1; i < 200001; i++){
        if(arr[i]){
            cnt++;
        }
    }

    cout << cnt << "\n";

    return 0;
}
```