[문제 바로가기](https://boj.kr/17945)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int A, B;
    cin >> A >> B;

    int val = A * A - B;
    if(val != 0){
        cout << A * -1 - sqrt(val) << " ";
        cout << A * -1 + sqrt(val) << "\n";
    }else{
        cout << A * -1 + sqrt(val) << "\n";
    }

    return 0;
}
```