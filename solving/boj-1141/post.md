[문제 바로가기](https://boj.kr/1141)

```c++
#include <bits/stdc++.h>

using namespace std;

bool checkPrefix(string, string);

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<string> words(N);
    for(int i = 0; i < N; i++){
        cin >> words[i];
    }

    sort(words.begin(), words.end());

    int cnt = N;
    for(int i = 0; i < N - 1; i++){
        if(checkPrefix(words[i], words[i + 1])){
            cnt--;
        }
    }

    cout << cnt << "\n";

    return 0;
}

bool checkPrefix(string prefix, string word){
    for(int i = 0; i < prefix.size(); i++){
        if(word[i] != prefix[i]){
            return false;
        }
    }

    return true;
}```