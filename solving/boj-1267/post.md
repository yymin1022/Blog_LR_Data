[문제 바로가기](https://boj.kr/1267)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int sumM = 0;
    int sumY = 0;
    for(int i = 0; i < N; i++){
        int T;
        cin >> T;

        sumM += (T / 60 + 1) * 15;
        sumY += (T / 30 + 1) * 10;
    }

    if(sumM < sumY){
        cout << "M " << sumM << "\n";
    }else if(sumM > sumY){
        cout << "Y " << sumY << "\n";
    }else{
        cout << "Y M " << sumM << "\n";
    }

    return 0;
}
```