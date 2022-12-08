[문제 바로가기](https://boj.kr/10886)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int cute = 0;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        if(input){
            cute++;
        }
    }

    if(cute > N - cute){
        cout << "Junhee is cute!" << "\n";
    }else{
        cout << "Junhee is not cute!" << "\n";
    }

    return 0;
}
```