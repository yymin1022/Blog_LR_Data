[문제 바로가기](https://boj.kr/1759)

```c++
#include <bits/stdc++.h>

using namespace std;

void find(string, int);

int L, C;
vector<char> alpha;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios::sync_with_stdio(false);

    cin >> L >> C;

    for(int i = 0; i < C; i++){
        char input;
        cin >> input;
        alpha.push_back(input);
    }

    sort(alpha.begin(), alpha.end());

    find("", 0);

    return 0;
}

void find(string cur, int idx){
    if(cur.size() == L){
        int co = 0, vo = 0;
        for(int i = 0; i < cur.size(); i++){
            if(cur[i] == 'a' || cur[i] == 'e' || cur[i] == 'i' || cur[i] == 'o' || cur[i] == 'u'){
                vo++;
            }else{
                co++;
            }
        }

        if(vo >= 1 && co >= 2){
            cout << cur << "\n";
        }
        
        return;
    }

    if(idx >= C){
        return;
    }

    find(cur + alpha[idx], idx + 1);
    find(cur, idx + 1);
}
```