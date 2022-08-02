[문제 바로가기](https://boj.kr/2477)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int K;
    cin >> K;

    int idxHeight;
    int idxWidth;
    int maxHeight = 0;
    int maxWidth = 0;
    vector<pair<int, int>> farm;
    for(int i = 0; i < 6; i++){
        int dir, len;
        cin >> dir >> len;

        farm.push_back(make_pair(dir, len));

        if(dir == 1 || dir == 2){
            if(maxWidth < len){
                idxWidth = i;
                maxWidth = len;
            }
        }else if(dir == 3 || dir == 4){
            if(maxHeight < len){
                idxHeight = i;
                maxHeight = len;
            }
        }
    }

    int cutHeight = farm[(idxWidth + 3) % 6].second;
    int cutWidth = farm[(idxHeight + 3) % 6].second;
    int farmSize = maxHeight * maxWidth - cutHeight * cutWidth;

    cout << K * farmSize << "\n";

    return 0;
}
```