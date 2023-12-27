[문제 바로가기](https://boj.kr/1384)

```c++
#include <algorithm>
#include <deque>
#include <iostream>
#include <queue>
#include <string>
#include <vector>
//#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int G = 1;
    while(true){
        int N;
        cin >> N;

        if(!N){
            break;
        }

        vector<pair<string, vector<string>>> data;
        for(int i = 0; i < N; i++){
            string name;
            cin >> name;

            vector<string> paper;
            for(int j = 1; j < N; j++){
                string input;
                cin >> input;
                paper.push_back(input);
            }

            data.push_back(make_pair(name, paper));
        }

        if(G > 1){
            cout << "\n";
        }

        cout << "Group" << " ";
        cout << G << "\n";

        bool flag = false;
        for(int i = 0; i < N; i++){
            for(int j = 0; j < N - 1; j++){
                if(data[i].second[j] == "N"){
                    int tmp = i - j - 1;
                    if(tmp < 0){
                        tmp += N;
                    }
                    flag = true;
                    cout << data[tmp].first << " ";
                    cout << "was nasty about" << " ";
                    cout << data[i].first << "\n";
                }
            }
        }

        if(!flag){
            cout << "Nobody was nasty" << "\n";
        }

        G++;
    }

    return 0;
}
```