[문제 바로가기](https://boj.kr/1676)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int cnt = 0;
    for(int i = N; i > 0; i--){
        int temp = i;

        while(temp){
            if(temp % 5 == 0){
                cnt++;
                temp /= 5;
            }else{
                break;
            }
        }
    }

    cout << cnt << "\n";

    return 0;
}```