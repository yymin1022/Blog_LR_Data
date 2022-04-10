[문제 바로가기](https://boj.kr/2493)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    int N;
    cin >> N;

    vector<int> height;
    for(int i = 1; i <= N; i++){
        int num;
        cin >> num;
        height.push_back(num);
    }

    stack<pair<int, int>> tops;
    for(int i = 0; i < N; i++){
        while(!tops.empty() && tops.top().second < height[i]){
            tops.pop();
        }

        if(tops.empty()){
            cout << 0 << " ";
        }else{
            cout << tops.top().first << " ";
        }

        tops.push(make_pair(i + 1, height[i]));
    }

    return 0;
}
```