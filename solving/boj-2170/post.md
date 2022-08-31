[문제 바로가기](https://boj.kr/2170)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> line;
    for(int i = 0; i <  N; i++){
        int start, end;
        cin >> start >> end;
        line.push_back(make_pair(start, end));
    }

    sort(line.begin(), line.end());

    int ans = 0;
    int start = line[0].first;
    int end = line[0].second;
    for(int i = 1; i < N; i++){
        int tempS = line[i].first;
        int tempE = line[i].second;

        if(end >= tempS){
            if(end < tempE){
                end = tempE;
            }
        }else{
            ans += end - start;
            start = tempS;
            end = tempE;
        }
    }

    ans += end - start;

    cout << ans << "\n";

    return 0;
}
```