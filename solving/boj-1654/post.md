[문제 바로가기](https://boj.kr/1654)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int K, N;
    cin >> K >> N;

    long long maxCable = 0;
    vector<long long> cables;
    for(int i = 0; i < K; i++){
        long long input;
        cin >> input;

        cables.push_back(input);
        maxCable = max(maxCable, input);
    }

    long long left = 1;
    long long right = maxCable;
    long long mid;
    long long result = 0;
    while(left <= right){
        mid = (left + right) / 2;

        long long sum = 0;
        for(int i = 0; i < K; i++){
            sum += cables[i] / mid;
        }

        if(sum >= N){
            left = mid + 1;
            result = max(result, mid);
        }else{
            right = mid - 1;
        }
    }

    cout << result << "\n";
    
    return 0;
}
```