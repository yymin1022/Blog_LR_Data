[문제 바로가기](https://boj.kr/25372)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N;
    cin >> N;
    
    for(int i = 0; i < N; i++){
        string pw;
        cin >> pw;
        
        if(pw.size() >= 6 && pw.size() <= 9){
            cout << "yes" << "\n";
        }else{
            cout << "no" << "\n";
        }
    }
    
    return 0;
}```