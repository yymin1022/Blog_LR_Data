[문제 바로가기](https://boj.kr/1406)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(void) {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string word;
    cin >> word;

    list<char> editor;
    for(int i = 0; i < word.size(); i++){
        editor.push_back(word[i]);
    }

    int M;
    cin >> M;

    auto cursor = editor.end();
    for(int i = 0; i < M; i++){
        char cmd;
        cin >> cmd;

        if(cmd == 'L'){
            if(cursor != editor.begin()){
                cursor--;
            }
        }else if(cmd == 'D'){
            if(cursor != editor.end()){
                cursor++;
            }
        }else if(cmd == 'B'){
            if(cursor != editor.begin()){
                cursor--;
                cursor = editor.erase(cursor);
            }
        }else if(cmd == 'P'){
            char input;
            cin >> input;

            editor.insert(cursor, input);
        }
    }

    for(auto i = editor.begin(); i != editor.end(); i++){
        cout << *i;
    }

    return 0;
}```