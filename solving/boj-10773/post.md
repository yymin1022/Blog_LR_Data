[문제 바로가기](https://boj.kr/10773)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);
    
    int K;
    cin >> K;

    int sum = 0;
    stack<int> numbers;
    for(int i = 0; i < K; i++){
        int num;
        cin >> num;

        if(num == 0){
            sum -= numbers.top();
            numbers.pop();
        }else{
            sum += num;
            numbers.push(num);
        }
    }

    cout << sum;

    return 0;
}
```