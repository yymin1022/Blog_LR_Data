[문제 바로가기](https://boj.kr/28136)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    int first;
    cin >> first;

    int before = first;
    for(int i = 1; i < N -1; i++){
        int input;
        cin >> input;

        if(input <= before){
            ans++;
        }
        before = input;
    }

    int last;
    cin >> last;

    if(last <= before){
        ans++;
    }
    if(first <= last){
        ans++;
    }

    cout << ans << "\n";

    return 0;
}
```