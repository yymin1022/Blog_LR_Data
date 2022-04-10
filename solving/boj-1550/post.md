[문제 바로가기](https://boj.kr/1550)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);
    
    string N;
    cin >> N;

    int answer = 0;
    for(int i = 0; i < N.size(); i++){
        if(N.at(i) >= 'A' && N.at(i) <= 'F'){
            answer += (N.at(i) - 55) * pow(16, N.size() - i - 1);
        }else{
            answer += (N.at(i) - 48) * pow(16, N.size() - i - 1);
        }
    }

    cout << answer;

    return 0;
}
```