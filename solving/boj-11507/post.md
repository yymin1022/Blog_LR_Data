[문제 바로가기](https://boj.kr/11507)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    map<char, int> count;
    map<char, map<int, bool>> data;
    for(int i = 0; i < S.size(); i += 3){
        char type = S[i];
        int num = (S[i + 1] - '0') * 10 + S[i + 2] - '0';

        if(data[type][num]){
            cout << "GRESKA" << "\n";
            return 0;
        }else{
            count[type]++;
            data[type][num] = true;
        }
    }

    cout << 13 - count['P'] << " ";
    cout << 13 - count['K'] << " ";
    cout << 13 - count['H'] << " ";
    cout << 13 - count['T'] << " ";

    return 0;
}
```