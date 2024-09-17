[문제 바로가기](https://boj.kr/1707)

```c++
#include <bits/stdc++.h>

using namespace std;

int isVisit[20001];
vector<int> arr[20001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int K;
    cin >> K;

    while(K--){
        int V, E;
        cin >> V >> E;

        memset(isVisit, 0, sizeof(isVisit));
        for(int i = 1; i <= V; i++){
            arr[i].clear();
        }

        for(int i = 0; i < E; i++){
            int from, to;
            cin >> from >> to;
            arr[from].push_back(to);
            arr[to].push_back(from);
        }

        bool flag = true;
        for(int i = 1; i <= V; i++){
            if(isVisit[i] == 0){
                queue<pair<int, bool>> bfsQ;
                bfsQ.push(make_pair(i, true));

                while(!bfsQ.empty() && flag){
                    int curNode = bfsQ.front().first;
                    bool curType = bfsQ.front().second;
                    bfsQ.pop();

                    isVisit[curNode] = curType ? 1 : -1;

                    for(int nextNode : arr[curNode]){
                        if(isVisit[nextNode] != 0){
                            if(isVisit[curNode] == isVisit[nextNode]){
                                cout << "NO" << "\n";
                                flag = false;
                                break;
                            }
                        }else{
                            bfsQ.push(make_pair(nextNode, !curType));
                        }
                    }
                }
            }
            if(!flag){
                break;
            }
        }

        if(flag){
            cout << "YES" << "\n";
        }
    }

    return 0;
}
```