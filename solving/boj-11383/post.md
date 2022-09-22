[문제 바로가기](https://boj.kr/11383)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N, M;
    cin >> N >> M;

    vector<string> word1(N);
    vector<string> word2(N);
    for(int i = 0; i < N; i++){
        cin >> word1[i];
    }
    for(int i = 0; i < N; i++){
        cin >> word2[i];
    }

    for(int i = 0; i < N; i++){
        string temp;
        for(int j = 0; j < M; j++){
            temp += word1[i][j];
            temp += word1[i][j];
        }

        if(temp != word2[i]){
            cout << "Not Eyfa" << "\n";
            return 0;
        }
    }

    cout << "Eyfa"<< "\n";

    return 0;
}
```