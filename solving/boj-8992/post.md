[문제 바로가기](https://boj.kr/8992)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isPalindrome(string str){
    int size = str.size();
    for(int i = 0; i < size / 2; i++){
        if(str[i] != str[size - i - 1]){
            return false;
        }
    }

    return true;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int K;
        cin >> K;

        vector<string> word;
        for(int i = 0; i < K; i++){
            string input;
            cin >> input;
            word.push_back(input);
        }

        string ans = "0";
        for(int i = 0; i < K; i++){
            for(int j = i + 1; j < K; j++){
                string tmp1 = word[i] + word[j];
                string tmp2 = word[j] + word[i];
                if(isPalindrome(tmp1)) ans = tmp1;
                if(isPalindrome(tmp2)) ans = tmp2;
            }
        }

        cout << ans << "\n";
    }

    return 0;
}
```