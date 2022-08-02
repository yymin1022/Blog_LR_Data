[문제 바로가기](https://boj.kr/1032)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(void) {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<string> files(50);
    for(int i = 0; i < N; i++){
        cin >> files[i];
    }

    for(int i = 0; i < files[0].size(); i++){
        bool isSame = true;

        for(int j = 1; j < N; j++){
            if(files[j][i] != files[0][i]){
                isSame = false;
                break;
            }
        }

        if(isSame){
            cout << files[0][i];
        }else{
            cout << "?";
        }
    }

    return 0;
}```