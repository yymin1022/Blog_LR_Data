[문제 바로가기](https://boj.kr/3613)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    string var;
    cin >> var;

    int type = 0;
    for(int i = 0; i < var.size(); i++){
        if(var[i] >= 'A' && var[i] <= 'Z'){
            if(i == 0 || type == 2){
                type = -1;
                break;
            }
            type = 1;
        }
        if(var[i] == '_'){
            if(var[i - 1] == '_' || i == 0 || i == var.size() - 1){
                type = -1;
                break;
            }
            if(type == 1){
                type = -1;
                break;
            }
            type = 2;
        }
    }

    if(type == -1){
        cout << "Error!" << "\n";
        return 0;
    }

    string ans = "";
    for(int i = 0; i < var.size(); i++){
        if(var[i] >= 'A' && var[i] <= 'Z'){
            ans.push_back('_');
            ans.push_back(var[i] + 32);
            continue;
        }
        if(var[i] == '_'){
            ans.push_back(var[i + 1] - 32);
            i++;
            continue;
        }
        ans.push_back(var[i]);
    }

    cout << ans << "\n";
    
    return 0;
}
```