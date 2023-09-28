[문제 바로가기](https://boj.kr/28445)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    vector<string> color(4);
    cin >> color[0] >> color[1] >> color[2] >> color[3];

    vector<string> ans;
    set<string> child;
    for(int i = 0; i < 4; i++){
        for(int j = 0; j < 4; j++){
            string tmp(color[i]);
            tmp.append(" ");
            tmp.append(color[j]);

            if(find(ans.begin(), ans.end(), tmp) == ans.end()){
                ans.push_back(tmp);
            }
        }
    }

    sort(ans.begin(), ans.end());

    for(int i = 0; i < ans.size(); i++){
        cout << ans[i] << "\n";
    }

    return 0;
}
```
