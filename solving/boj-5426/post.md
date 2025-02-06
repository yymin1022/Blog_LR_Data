[문제 바로가기](https://boj.kr/5426)

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
        string S;
        cin >> S;

        int len = sqrt(S.length());
        vector<string> arr(len);
        for(int i = 0; i < len; i++){
            for(int j = 0; j < len; j++){
                arr[i].push_back(S[j + len * i]);
            }
        }

        string ans;
        for(int j = len - 1; j >= 0; j--){
            for(int i = 0; i < len; i++){
                ans.push_back(arr[i][j]);
            }
        }

        cout << ans << "\n";
    }

    return 0;
}
```