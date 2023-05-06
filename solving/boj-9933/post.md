[문제 바로가기](https://boj.kr/9933)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<string> password;
    vector<string> rPassword;
    for(int i = 0; i < N; i++){
        string S;
        cin >> S;
        password.push_back(S);
        reverse(S.begin(), S.end());
        rPassword.push_back(S);
    }

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            if(password[i] == rPassword[j]){
                cout << password[i].size() << " ";
                cout << password[i][password[i].size() / 2] << "\n";
                return 0;
            }
        }
    }

    return 0;
}
```