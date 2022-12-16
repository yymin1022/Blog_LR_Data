[문제 바로가기](https://boj.kr/11931)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N;
    cin >> N;

    vector<int> num;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        num.push_back(input);
    }

    sort(num.begin(), num.end());
    reverse(num.begin(), num.end());

    for(int i = 0; i < N; i++){
        cout << num[i] << "\n";
    }

    return 0;
}
```