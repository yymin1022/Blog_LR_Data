[문제 바로가기](https://boj.kr/1107)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isBroken[10];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int M, N;
    cin >> N >> M;

    for(int i = 0; i < M; i++){
        int temp;
        cin >> temp;
        isBroken[temp] = true;
    }

    if(N == 100){
        cout << 0 << "\n";
        return 0;
    }

    int answer = abs(N - 100);
    for(int i = 0; i < 1000000; i++){
        bool isPossible = true;
        int temp = 0;
        int tempI = i;

        if(i == 0){
            if(isBroken[0]){
                isPossible = false;
            }else{
                temp = 1;
            }
        }

        while(tempI > 0){
            if(isBroken[tempI % 10]){
                isPossible = false;
                break;
            }
            temp++;
            tempI /= 10;
        }

        if(isPossible){
            if(answer > abs(N - i) + temp){
                answer = abs(N - i) + temp;
            }
        }
    }

    cout << answer << "\n";
    
    return 0;
}
```