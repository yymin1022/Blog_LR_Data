[문제 바로가기](https://boj.kr/22866)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> buildings(N + 1);
    for(int i = 1; i <= N; i++){
        int input;
        cin >> input;
        buildings[i] = make_pair(i, input);
    }

    stack<pair<int, int>> tempStack;
    vector<int> cnt(N + 1);
    vector<vector<int>> near(N + 1,vector<int>(2,N + 2));
    for(int i = 1; i <= N; i++){
        while(!tempStack.empty() && tempStack.top().second <= buildings[i].second){
            tempStack.pop();
        }

        cnt[i] += tempStack.size();

        if(!tempStack.empty()){
            int distance = abs(tempStack.top().first - i);

            if(distance <= near[i][1]) {
                near[i][0] = tempStack.top().first;
                near[i][1] = distance;
            }
        }

        tempStack.push(buildings[i]);
    }

    while(!tempStack.empty()){
        tempStack.pop();
    }

    for(int i = N; i >= 1; i--){
        while(!tempStack.empty() && tempStack.top().second <= buildings[i].second){
            tempStack.pop();
        }

        cnt[i] += tempStack.size();

        if(!tempStack.empty()){
            int distance = abs(tempStack.top().first - i);

            if(distance < near[i][1]) {
                near[i][0] = tempStack.top().first;
                near[i][1] = distance;
            }else if(distance == near[i][1] && tempStack.top().first < near[i][0]){
                near[i][0] = tempStack.top().first;
            }
        }

        tempStack.push(buildings[i]);
    }

    for(int i = 1; i <= N; i++){
        if(!cnt[i]){
            cout << 0 << "\n";
        }else{
            cout << cnt[i] << " " << near[i][0] << "\n";
        }
    }

    return 0;
}```