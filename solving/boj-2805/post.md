[문제 바로가기](https://boj.kr/2805)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<long long> trees;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;

        trees.push_back(input);
    }

    sort(trees.begin(), trees.end());

    long long left = 0;
    long long mid;
    long long right = trees[N - 1];
    long long result = 0;

    while(left <= right){
        mid = (left + right) / 2;

        long long sum = 0;
        for(int i = 0; i < N; i++){
            if(trees[i] > mid){
                sum += trees[i] - mid;
            }
        }

        if(sum < M){
            right = mid - 1;
        }else{
            left = mid + 1;
            result = mid;
        }
    }

    cout << result << "\n";
    
    return 0;
}```