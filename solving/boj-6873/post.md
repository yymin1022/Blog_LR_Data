[문제 바로가기](https://boj.kr/6873)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string startDir;
    cin >> startDir;

    vector<pair<string, string>> route;
    while(true){
        string direction, street;
        cin >> street;

        if(street == "SCHOOL"){
            break;
        }

        cin >> direction;
        route.push_back(make_pair(direction, street));
    }

    reverse(route.begin(), route.end());

    for(int i = 0; i < route.size(); i++){
        cout << "Turn " << (route[i].first == "R" ? "LEFT" : "RIGHT") << " onto " << route[i].second << " street." << "\n";
    }

    cout << "Turn " << (startDir == "R" ? "LEFT" : "RIGHT") << " into your HOME." << "\n";

    return 0;
}
```