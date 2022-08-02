[문제 바로가기](https://boj.kr/17609)

```c++
#include <bits/stdc++.h>

using namespace std;

int check(string, bool);

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int i = 0; i < T; i++){
        string word;
        cin >> word;

        cout << check(word, false) << "\n";
    }

    return 0;
}

int check(string word, bool isPseudo){
    int fromL = 0;
    int fromR = word.size() - 1;

    while(fromL < fromR){
        if(word[fromL] != word[fromR]){
            if(isPseudo){
                return 2;
            }else{
                if(!check(word.substr(fromL, fromR - fromL), true)){
                    return 1;
                }else if(!check(word.substr(fromL + 1, fromR - fromL), true)) {
                    return 1;
                }else{
                    return 2;
                }
            }
        }

        fromL++;
        fromR--;
    }

    return 0;
}```