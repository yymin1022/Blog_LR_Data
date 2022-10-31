[문제 바로가기](https://boj.kr/20499)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string input;
    cin >> input;

    int tmp = 0;
    vector<string> kda_s;
    for(int i = 0; i < input.size(); i++){
        if(input[i] == '/'){
            kda_s.push_back(input.substr(tmp, i - tmp + 1));
            tmp = i + 1;
        }
    }

    kda_s.push_back(input.substr(tmp, input.size() - tmp));

    int kda[3];
    for(int i = 0; i < 3; i++){
        kda[i] = stoi(kda_s[i]);
    }

    if(kda[0] + kda[2] < kda[1] || !kda[1]){
        cout << "hasu" << "\n";
    }else{
        cout << "gosu" << "\n";
    }

    return 0;
}
```