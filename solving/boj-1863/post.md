[문제 바로가기](https://boj.kr/1863)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int result = 0;
    stack<int> building;
    for(int i = 0; i < N; i++){
        int height, temp;
        cin >> temp >> height;

        while(!building.empty() && building.top() > height){
            if(building.top() > 0){
                result++;
            }
            building.pop();
        }

        if(building.empty() || building.top() != height){
            building.push(height);
        }
    }

    while(!building.empty()){
        if(building.top() > 0){
            result++;
        }
        building.pop();
    }

    cout << result << "\n";

    return 0;
}```