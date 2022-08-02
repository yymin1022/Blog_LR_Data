[문제 바로가기](https://boj.kr/2075)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios::sync_with_stdio(false);

    int N;
    cin >> N;

    priority_queue<int> nums;
    for(int i = 0; i < N * N; i++){
        int input;
        cin >> input;

        nums.push(input * -1);

        if(i >= N){
            nums.pop();
        }
    }

    cout << nums.top() * -1 << "\n";
}```