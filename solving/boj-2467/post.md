[문제 바로가기](https://boj.kr/2467)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(void) {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<long long> liquid;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        liquid.push_back(input);
    }

    int fromStart = 0;
    int fromEnd = N - 1;
    long long sum = 9876543210;
    long long result[2];
    while(fromStart < fromEnd){
        long long temp = liquid[fromStart] + liquid[fromEnd];

        if(abs(temp) < sum){
            result[0] = liquid[fromStart];
            result[1] = liquid[fromEnd];
            sum = abs(temp);
        }

        if(temp < 0){
            fromStart++;
        }else{
            fromEnd--;
        }
    }

    cout << result[0] << " " << result[1] << "\n";

    return 0;
}```