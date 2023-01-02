[문제 바로가기](https://boj.kr/14582)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    vector<int> wool(10, 0);
    for(int i = 1; i <= 9; i++){
        int input;
        cin >> input;
        wool[i] = wool[i - 1] + input;
    }

    vector<int> star(10, 0);
    for(int i = 1; i <= 9; i++){
        int input;
        cin >> input;
        star[i] = star[i - 1] + input;
    }

    bool isWool = false;
    for(int i = 1; i <= 9; i++){
        if(wool[i] > star[i - 1]){
            isWool = true;
            break;
        }
    }

    cout << (isWool ? "Yes" : "No") << "\n";

    return 0;
}
```