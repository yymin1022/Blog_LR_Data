[문제 바로가기](https://boj.kr/9996)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    string pattern;
    cin >> N >> pattern;

    for(int i = 0; i < N; i++){
        string file;
        cin >> file;

        if(file.size() < pattern.size() - 1){
            cout << "NE" << "\n";
            continue;
        }

        bool isErr = false;
        for(int j = 0; j < file.size(); j++){
            if(pattern[j] == '*'){
                break;
            }

            if(pattern[j] != file[j]){
                isErr = true;
                break;
            }
        }

        for(int j = 0; j < file.size(); j++){
            if(pattern[pattern.size() - j - 1] == '*'){
                break;
            }

            if(pattern[pattern.size() - j - 1] != file[file.size() - j - 1]){
                isErr = true;
                break;
            }
        }

        cout << (isErr ? "NE" : "DA") << "\n";
    }

    return 0;
}
```