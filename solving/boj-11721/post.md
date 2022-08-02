[문제 바로가기](https://boj.kr/11721)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(void) {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string word;
    cin >> word;

    for(int i = 1; i <= word.size(); i++){
        cout << word[i - 1];
        if(i % 10 == 0){
            cout << "\n";
        }
    }

    return 0;
}```