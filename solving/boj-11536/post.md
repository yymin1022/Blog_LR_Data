[문제 바로가기](https://boj.kr/11536)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<string> name;
    vector<string> tmp;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        name.push_back(input);
        tmp.push_back(input);
    }

    sort(tmp.begin(), tmp.end());
    if (name == tmp){
        cout << "INCREASING" << "\n";
        return 0;
    }

    sort(tmp.begin(), tmp.end(), greater<string>());
    if (name == tmp){
        cout << "DECREASING" << "\n";
        return 0;
    }

    cout << "NEITHER" << "\n";

    return 0;
}
```