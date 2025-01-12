[문제 바로가기](https://boj.kr/23305)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    map<int, int> data;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        data[input]++;
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        if(data.count(input) == 0 || data[input] == 0){
            ans++;
        }else{
            data[input]--;
        }
    }

    cout << ans << "\n";

    return 0;
}
```