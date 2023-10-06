[문제 바로가기](https://boj.kr/15719)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<bool> arr(10000000, false);
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        if(!arr[input]){
            arr[input] = true;
        }else{
            cout << input << "\n";
            return 0;
        }
    }

    return 0;
}
```