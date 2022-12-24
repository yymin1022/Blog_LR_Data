[문제 바로가기](https://boj.kr/6321)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N;
    cin >> N;
    
    vector<string> word;
    word.push_back("");
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        word.push_back(input);
    }
    
    for(int i = 1; i <= N; i++){
        cout << "String #" << i << "\n";
        
        for(int j = 0; j < word[i].size(); j++){
            if(word[i][j] == 'Z'){
                cout << 'A';
            }else{
                cout << (char)((int)word[i][j] + 1);
            }
        }
        
        cout << "\n\n";
    }
    
    return 0;
}
```