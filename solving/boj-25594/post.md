[문제 바로가기](https://boj.kr/25594)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string hg[26] = {"aespa", "baekjoon", "cau", "debug", "edge", "firefox", "golang", "haegang", "iu", "java", "kotlin", "lol", "mips", "null", "os", "python", "query", "roka", "solvedac", "tod", "unix", "virus", "whale", "xcode", "yahoo", "zebra"};

    string S;
    cin >> S;

    int cur = 0;
    string ans = "";
    while(cur < S.size()){
        char curC = S[cur];
        string curHG = hg[curC - 97];

        for(int i = 0; i < curHG.size(); i++){
            if(S[cur + i] != curHG[i]){
                cout << "ERROR!" << "\n";
                return 0;
            }
        }

        ans += curC;
        cur += curHG.size();
    }

    cout << "It's HG!" << "\n";
    cout << ans << "\n";

    return 0;
}
```