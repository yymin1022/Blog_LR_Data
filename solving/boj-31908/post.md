[문제 바로가기](https://boj.kr/31908)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    map<string, vector<string>> data;
    for(int i = 0; i < N; i++){
        string name, ring;
        cin >> name >> ring;

        if(ring != "-"){
            data[ring].push_back(name);
        }
    }

    int ansCnt = 0;
    vector<string> ansName;
    for(auto iter = data.begin(); iter != data.end(); iter++){
        if(iter->second.size() == 2){
            ansCnt++;
            ansName.push_back(iter->second[0]);
            ansName.push_back(iter->second[1]);
        }
    }

    cout << ansCnt << "\n";
    for(int i = 0; i < ansName.size(); i++){
        cout << ansName[i] << " ";
        if(i % 2){
            cout << "\n";
        }
    }

    return 0;
}
```
