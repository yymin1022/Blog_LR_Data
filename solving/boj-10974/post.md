[문제 바로가기](https://boj.kr/10974)

```python
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> nums;
    for(int i = 1; i <= N; i++){
        nums.push_back(i);
    }

    while(true){
        for(int i = 0; i < N; i++){
            cout << nums[i] << " ";
        }

        cout << "\n";

        if(!next_permutation(nums.begin(), nums.end())){
            break;
        }
    }

    return 0;
}
```