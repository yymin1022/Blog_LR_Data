[문제 바로가기](https://boj.kr/12605)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    cin.ignore();
    for(int i = 1; i <= N; i++){
        string S;
        getline(cin, S);

        string tmp = "";
        vector<string> arr;
        for(int j = 0; j < S.size(); j++){
            if(S[j] == ' '){
                arr.push_back(tmp);
                tmp = "";
            }else{
                tmp += S[j];
            }
        }

        arr.push_back(tmp);

        cout << "Case #" << i << ": ";
        for(int j = arr.size() - 1; j >= 0; j--){
            cout << arr[j] << " ";
        }
        cout << "\n";
    }

    return 0;
}
```