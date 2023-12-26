[문제 바로가기](https://boj.kr/4446)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    vector<char> consonant = {'b', 'k', 'x', 'z', 'n', 'h', 'd', 'c', 'w', 'g', 'p', 'v', 'j', 'q', 't', 's', 'r', 'l', 'm', 'f'};
    vector<char> consonantCap = {'B', 'K', 'X', 'Z', 'N', 'H', 'D', 'C', 'W', 'G', 'P', 'V', 'J', 'Q', 'T', 'S', 'R', 'L', 'M', 'F'};
    vector<char> vowel = {'a', 'i', 'y', 'e', 'o', 'u'};
    vector<char> vowelCap = {'A', 'I', 'Y', 'E', 'O', 'U'};

    string S;
    while(getline(cin, S)){
        for(int i = 0; i < S.size(); i++){
            int idx = find(consonant.begin(), consonant.end(), S[i]) - consonant.begin();
            if(idx < 20){
                idx += 10;
                idx %= 20;
                cout << consonant[idx];
                continue;
            }

            idx = find(consonantCap.begin(), consonantCap.end(), S[i]) - consonantCap.begin();
            if(idx < 20){
                idx += 10;
                idx %= 20;
                cout << consonantCap[idx];
                continue;
            }

            idx = find(vowel.begin(), vowel.end(), S[i]) - vowel.begin();
            if(idx < 6){
                idx += 3;
                idx %= 6;
                cout << vowel[idx];
                continue;
            }

            idx = find(vowelCap.begin(), vowelCap.end(), S[i]) - vowelCap.begin();
            if(idx < 6){
                idx += 3;
                idx %= 6;
                cout << vowelCap[idx];
                continue;
            }

            cout << S[i];
        }
        cout << "\n";
    }

    return 0;
}

```