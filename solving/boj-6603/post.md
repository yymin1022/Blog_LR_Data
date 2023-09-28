[문제 바로가기](https://boj.kr/6603)

```c++
#include <bits/stdc++.h>

using namespace std;

vector<int> sel;

void dfs(vector<int> num, int idx, int cnt){
    if(sel.size() == 6){
        for(int i = 0; i < sel.size(); i++){
            cout << sel[i] << " ";
        }
        cout << "\n";
        return;
    }

    for(int i = idx; i < num.size(); i++){
        sel.push_back(num[i]);
        dfs(num, i + 1, cnt + 1);
        sel.pop_back();
    }
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int K;
    cin >> K;

    while(K){
        vector<int> num;
        for(int i = 0; i < K; i++){
            int input;
            cin >> input;
            num.push_back(input);
        }

        dfs(num, 0, 0);
        cout << "\n";

        cin >> K;
    }

    return 0;
}
```