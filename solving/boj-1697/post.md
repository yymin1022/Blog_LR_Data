[문제 바로가기](https://boj.kr/1697)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    int cnt = 0;

    queue<int> bfs;
    vector<bool> isVisit(100999, false);
    bfs.push(N);
    isVisit[N] = true;

    while(!bfs.empty()){
        int size = bfs.size();

        for(int i = 0; i < size; i++){
            int cur = bfs.front();
            bfs.pop();

            if(cur == K){
                cout << cnt << "\n";
                return 0;
            }

            if(cur - 1 >= 0 && !isVisit[cur - 1]){
                bfs.push(cur - 1);
                isVisit[cur - 1] = true;
            }
            if(cur + 1 <= 100999 && !isVisit[cur + 1]){
                bfs.push(cur + 1);
                isVisit[cur + 1] = true;
            }
            if(cur * 2 <= 100999 && !isVisit[cur * 2]){
                bfs.push(cur * 2);
                isVisit[cur * 2] = true;
            }
        }

        cnt++;
    }

    return 0;
}```