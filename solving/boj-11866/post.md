[문제 바로가기](https://boj.kr/11866)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);
    
    int N, K;
    cin >> N >> K;

    queue<int> nums;
    for(int i = 0; i < N; i++){
        nums.push(i + 1);
    }

    cout << "<";
    while(!nums.empty()){
        for(int i = 0; i < K - 1; i++){
            nums.push(nums.front());
            nums.pop();
        }

        if(nums.front() != K){
            cout << ", ";
        }
        
        cout << nums.front();
        nums.pop();
    }
    cout << ">";

    return 0;
}
```