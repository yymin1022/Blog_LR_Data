[문제 바로가기](https://boj.kr/11286)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> nums;
    for(int i = 0; i < N; i++){
        int X;
        cin >> X;

        if(X != 0){
            int tempX = X;
            if(X < 0){
                tempX *= -1;
            }

            nums.push(make_pair(tempX, X));
        }else{
            if(!nums.empty()){
                cout << nums.top().second << "\n";
                nums.pop();
            }else{
                cout << 0 << "\n";
            }
        }
    }

    return 0;
}
```