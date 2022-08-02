[문제 바로가기](https://boj.kr/11651)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> points;
    for(int i = 0; i < N; i++){
        int x, y;
        cin >> x >> y;

        points.push_back(make_pair(y, x));
    }

    sort(points.begin(), points.end());

    for(int i = 0; i < N; i++){
        cout << points[i].second << " " << points[i].first << "\n";
    }
    
    return 0;
}```