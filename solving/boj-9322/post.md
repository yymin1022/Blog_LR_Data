[문제 바로가기](https://boj.kr/9322)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        map<string, int> first;
        for (int i = 0; i < N; i++){
            string input;
            cin >> input;
            first[input] = i;
        }

        map<int, int> second;
        for (int i = 0; i < N; i++){
            string input;
            cin >> input;
            second[first[input]] = i;
        }

        vector<string> cipher;
        for (int i = 0; i < N; i++){
            string input;
            cin >> input;
            cipher.push_back(input);
        }

        for (int i = 0; i < N; i++){
            cout << cipher[second[i]] << " ";
        }
        cout << "\n";
    }

    return 0;
}
```