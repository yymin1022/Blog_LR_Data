[문제 바로가기](https://boj.kr/1092)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> crain;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        crain.push_back(input);
    }

    int M;
    cin >> M;

    vector<int> box;
    for(int i = 0; i < M; i++){
        int input;
        cin >> input;
        box.push_back(input);
    }

    sort(box.begin(), box.end(), greater<int>());
    sort(crain.begin(), crain.end(), greater<int>());

    if(box[0] > crain[0]){
        cout << -1 << "\n";
        return 0;
    }

    int time = 0;
    while(box.size()){
        time++;
        for(int i = 0; i < crain.size(); i++){
            for(int j = 0; j < box.size(); j++){
                if(box[j] <= crain[i]){
                    box.erase(box.begin() + j);
                    break;
                }
            }
        }
    }

    cout << time << "\n";

    return 0;
}
```