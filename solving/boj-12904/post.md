[문제 바로가기](https://boj.kr/12904)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string A, B;
    cin >> A >> B;

    while(B.length() > A.length()){
        if(B.back() == 'A'){
            B.pop_back();
        }else{
            B.pop_back();
            reverse(B.begin(), B.end());
        }
    }

    if(A == B){
        cout << 1 << "\n";
    }else{
        cout << 0 << "\n";
    }

    return 0;
}
```