[문제 바로가기](https://boj.kr/6198)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N;
    cin >> N;

    long long ans = 0;
    stack<int> building;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        if(building.empty()){
            building.push(input);
        }else{
            while(!building.empty() && building.top() <= input){
                building.pop();
            }

            ans += building.size();
            building.push(input);
        }
    }

    cout << ans << "\n";
    
    return 0;
}
```