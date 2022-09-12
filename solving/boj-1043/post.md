[문제 바로가기](https://boj.kr/1043)

```c++
#include <bits/stdc++.h>

using namespace std;

int Find(int);
void Union(int, int);

int N, M;
int parent[51];
vector<int> arr[51];
vector<int> people;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 1; i <= N; i++){
        parent[i] = i;
    }

    int know;
    cin >> know;

    for(int i = 0; i < know; i++){
        int input;
        cin >> input;
        people.push_back(input);
    }

    for(int i = 0; i < M; i++){
        int input;
        cin >> input;

        int from, to;
        for(int j = 0; j < input; j++){
            cin >> to;
            arr[i].push_back(to);

            if(j){
                Union(from, to);
            }

            from = to;
        }
    }

    int ans = 0;
    if(!know){
        cout << M << "\n";
        return 0;
    }

    for(int i = 0; i < M; i++){
        bool isOK = true;
        for(int j = 0; j < arr[i].size(); j++){
            int cur = arr[i][j];
            for(int k = 0; k < people.size(); k++){
                if(Find(cur) == Find(people[k])){
                    isOK = false;
                    break;
                }
            }

            if(!isOK){
                break;
            }
        }

        if(isOK){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}

int Find(int node){
    if(parent[node] == node){
        return node;
    }

    parent[node] = Find(parent[node]);
    return parent[node];
}

void Union(int x, int y){
    x = Find(x);
    y = Find(y);

    parent[x] = y;
}
```