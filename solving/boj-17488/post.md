[문제 바로가기](https://boj.kr/17488)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> L(M + 1);
    for(int i = 1; i <= M; i++){
        cin >> L[i];
    }

    vector<int> ans[1001];
    vector<int> queue[1001];
    for(int i = 1; i <= N; i++){
        int input;
        cin >> input;
        while(input > 0){
            queue[input].push_back(i);
            cin >> input;
        }
    }

    for(int i = 1; i <= M; i++){
        if(queue[i].size() <= L[i]){
            for(int j = 0; j < queue[i].size(); j++){
                if(queue[i][j] > 0){
                    ans[queue[i][j]].push_back(i);
                    queue[i][j] = 0;
                }
            }
        }
    }

    for(int i = 1; i <= N; i++){
        int input;
        cin >> input;
        while(input > 0){
            queue[input].push_back(i);
            cin >> input;
        }
    }

    for(int i = 1; i <= M; i++){
        if(queue[i].size() <= L[i]){
            for(int j = 0; j < queue[i].size(); j++){
                if(queue[i][j] > 0){
                    ans[queue[i][j]].push_back(i);
                    queue[i][j] = 0;
                    L[i]--;
                }
            }
        }
    }

    for(int i = 1; i <= N; i++){
        if(ans[i].size() > 0){
            sort(ans[i].begin(), ans[i].end());
            for(int j = 0; j < ans[i].size(); j++){
                cout << ans[i][j] << " ";
            }
            cout << "\n";
        }else{
            cout << "망했어요" << "\n";
        }
    }

    return 0;
}
```