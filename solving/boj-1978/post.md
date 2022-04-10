[문제 바로가기](https://boj.kr/1978)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int count = 0;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        if(input > 1){
            for(int j = 2; j <= sqrt(input); j++){
                if(input % j == 0){
                    count--;
                    break;
                }
            }
            
            count++;
        }
    }

    cout << count << "\n";
    
    return 0;
}
```