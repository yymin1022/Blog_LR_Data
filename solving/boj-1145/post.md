[문제 바로가기](https://boj.kr/1145)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    vector<int> num(5);
    for(int i = 0; i < 5; i++){
        cin >> num[i];
    }

    sort(num.begin(), num.end());

    for(int i = num[0]; i <= num[2] * num[3] * num[4]; i++){
        int cnt = 0;

        if(!(i % num[0])){
            cnt++;
        }

        if(!(i % num[1])){
            cnt++;
        }

        if(!(i % num[2])){
            cnt++;
        }

        if(!(i % num[3])){
            cnt++;
        }

        if(!(i % num[4])){
            cnt++;
        }

        if(cnt > 2){
            cout << i << "\n";
            return 0;
        }
    }

    return 0;
}
```