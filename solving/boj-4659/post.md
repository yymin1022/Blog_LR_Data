[문제 바로가기](https://boj.kr/4659)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVowel(char c){
    if(c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u'){
        return true;
    }
    return false;
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string password;
    cin >> password;

    while(password != "end"){
        bool isOK = true;

        int vowel = 0;
        for(int i = 0; i < password.size(); i++){
            if(i >= 2){
                if((isVowel(password[i]) == isVowel(password[i - 1])) && (isVowel(password[i - 1]) == isVowel(password[i - 2]))){
                    isOK = false;
                    break;
                }
            }

            if(isVowel(password[i])){
                vowel++;
            }

            if(i >= 1){
                if(password[i] == password[i - 1] && password[i] != 'e' && password[i] != 'o'){
                    isOK = false;
                    break;
                }
            }
        }

        if(vowel == 0){
            isOK = false;
        }

        cout << "<" << password << "> is ";
        if(!isOK){
            cout << "not ";
        }
        cout << "acceptable." << "\n";

        cin >> password;
    }

    return 0;
}
```