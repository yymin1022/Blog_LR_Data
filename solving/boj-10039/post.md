[문제 바로가기](https://boj.kr/10039)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int sum = 0;
    for(int i = 0; i < 5; i++){
        int input;
        cin >> input;
        
        if(input < 40){
            sum += 40;
        }else{
            sum += input;
        }
    }
    
    cout << sum / 5 << "\n";
    
    return 0;
}```