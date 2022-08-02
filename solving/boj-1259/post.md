[문제 바로가기](https://boj.kr/1259)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    while(1){
        int N;
        cin >> N;

        if(!N){
            break;
        }
        
        int temp = 0;
        int tempN = N;
        while(tempN){
            temp *= 10;
            temp += tempN % 10;
            tempN /= 10;
        }

        if(N == temp){
            cout << "yes" << "\n";
        }else{
            cout << "no" << "\n";
        }
    }
    
    return 0;
}```