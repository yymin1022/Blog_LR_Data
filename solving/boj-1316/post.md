[문제 바로가기](https://boj.kr/1316)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    int N;
    cin >> N;

    int count = 0;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        vector<int> ascii;
        for(int j = 0; j < 26; j++){
            ascii.push_back(0);
        }

        bool isGroup = true;
        for(int j = 0; j < input.size(); j++){
            if(ascii[input[j] - 'a'] != 0 && input[j] != input[j - 1]){
                isGroup = false;
                break;
            }else{
                ascii[input[j] - 'a']++;
            }
        }

        if(isGroup){
            count++;
        }
    }

    cout << count;

    return 0;
}
```