[문제 바로가기](https://boj.kr/19637)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<string> dataName;
    vector<int> dataVal;
    for(int i = 0; i < N; i++){
        string name;
        int val;
        cin >> name >> val;
        dataName.push_back(name);
        dataVal.push_back(val);
    }

    while(M--){
        int val;
        cin >> val;

        cout << dataName[lower_bound(dataVal.begin(), dataVal.end(), val) - dataVal.begin()] << "\n";
    }

    return 0;
}
```