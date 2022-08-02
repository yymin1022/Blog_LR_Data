[문제 바로가기](https://boj.kr/3009)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    vector<pair<int, int>> points;
    for(int i = 0; i < 3; i++){
        int x, y;
        cin >> x >> y;
        points.push_back(make_pair(x, y));
    }

    if(points[0].first == points[1].first){
        cout << points[2].first << " ";
    }else if(points[0].first == points[2].first){
        cout << points[1].first << " ";
    }else{
        cout << points[0].first << " ";
    }

    if(points[0].second == points[1].second){
        cout << points[2].second << "\n";
    }else if(points[0].second == points[2].second){
        cout << points[1].second << "\n";
    }else{
        cout << points[0].second << "\n";
    }

    return 0;
}```