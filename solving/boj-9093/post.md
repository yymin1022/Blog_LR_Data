[문제 바로가기](https://boj.kr/9093)

```c++
#include <iostream>
#include <queue>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    cin.ignore();
    while(T--){
        string S;
        getline(cin, S);

        int idx = 0;
        for(int i = 0; i < S.size(); i++){
            if(S[i] == ' '){
                int tmp = i - 1;
                for(int j = tmp; j >= idx; j--){
                    cout << S[j];
                }

                cout << " ";
                idx = i + 1;
            }
        }

        for(int i = S.size() - 1; i >= idx; i--){
            cout << S[i];
        }
        cout << "\n";
    }

    return 0;
}
```