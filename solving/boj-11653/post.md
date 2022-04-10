[문제 바로가기](https://boj.kr/11653)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    if(N == 1){
        return 0;
    }

    vector<pair<int, int>> nums;
    for(int i = 2; i <= N; i++){
        int count = 0;
        while(!(N % i)){
            count++;
            N /= i;
        }

        nums.push_back(make_pair(i, count));
    }

    for(int i = 0; i < nums.size(); i++){
        for(int j = 0; j < nums[i].second; j++){
            cout << nums[i].first << "\n";
        }
    }

    return 0;
}
```