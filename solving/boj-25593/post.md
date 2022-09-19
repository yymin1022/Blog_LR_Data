[문제 바로가기](https://boj.kr/25593)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int work[4] = {4, 6, 4, 10};
    map<string, int> workTime;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < 4; j++){
            for(int k = 0; k < 7; k++){
                string name;
                cin >> name;

                if(name != "-"){
                    workTime[name] += work[j];
                }
            }
        }
    }

    if(workTime.empty()){
        cout << "Yes" << "\n";
        return 0;
    }

    vector<int> workTimeArr;
    for(auto & iter : workTime){
        workTimeArr.push_back(iter.second);
    }

    sort(workTimeArr.begin(), workTimeArr.end());

    if(workTimeArr[workTimeArr.size() - 1] - workTimeArr[0] > 12){
        cout << "No" << "\n";
    }else{
        cout << "Yes" << "\n";
    }

    return 0;
}
```