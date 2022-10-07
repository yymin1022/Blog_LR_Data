[문제 바로가기](https://boj.kr/11509)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int cnt = 0;
    vector<int> arrow(1000001, 0);
    for(int i = 0; i < N; i++){
        int balloon;
        cin >> balloon;

        if(arrow[balloon + 1]){
            arrow[balloon + 1]--;
        }else{
            cnt++;
        }

        arrow[balloon]++;
    }

    cout << cnt << "\n";

    return 0;
}
```