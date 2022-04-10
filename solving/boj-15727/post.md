[문제 바로가기](https://boj.kr/15727)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);
    
    int L;
    cin >> L;
    
    int count = 0;
    int jump = 5;
    int moved = 0;
    while(moved != L){
        if(L - moved < jump){
            jump--;
            continue;
        }
        
        moved += jump;
        count++;
    }
    
    cout << count;
    
    return 0;
}
```