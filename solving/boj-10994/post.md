[문제 바로가기](https://boj.kr/10994)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int r = N * 4 - 3;
    int c = N * 4 - 3, center = N * 2 - 2;
    for(int i = 0; i < r; i++){
        for(int j = 0; j < c; j++){
            if(max(abs(i - center), abs(j - center)) % 2 == 1){
                cout << " ";
            }else{
                cout << "*";
            }
        }

        cout << "\n";
    }

    return 0;
}
```