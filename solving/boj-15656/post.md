[문제 바로가기](https://boj.kr/15656)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    int N, M;
    cin >> N >> M;

    vector<int> numbers;
    for(int i = 0; i < N; i++){
        int inputN;
        cin >> inputN;
        numbers.push_back(inputN);
    }

    int answer = 0;
    for(int i = 0; i < N - 2; i++){
        for(int j = i + 1; j < N - 1; j++){
            for(int k = j + 1; k < N; k++){
                int sum = numbers[i] + numbers[j] + numbers[k];
                if(answer < sum && sum <= M){
                    answer = sum;
                }
            }
        }
    }

    cout << answer;
}
```