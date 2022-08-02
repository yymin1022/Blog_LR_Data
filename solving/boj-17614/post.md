[문제 바로가기](https://boj.kr/17614)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int N;
    cin >> N;

    int cnt = 0;
    for(int i = 1; i <= N; i++){
        string temp = to_string(i);

        for(char c : temp){
            if(c == '3' || c == '6' || c == '9'){
                cnt++;
            }
        }
    }

    cout << cnt << "\n";

    return 0;
}```