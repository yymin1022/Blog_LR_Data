[문제 바로가기](https://boj.kr/1543)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string doc, word;
    getline(cin, doc);
    getline(cin, word);

    int cnt = 0;
    for(int i = 0; i < doc.size(); i++){
        bool isFound = true;
        for(int j = 0; j < word.size(); j++){
            if(doc[i + j] != word[j]){
                isFound = false;
                break;
            }
        }

        if(isFound){
            cnt++;
            i += word.size() - 1;
        }
    }

    cout << cnt << "\n";

    return 0;
}

```