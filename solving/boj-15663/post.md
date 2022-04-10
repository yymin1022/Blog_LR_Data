[문제 바로가기](https://boj.kr/15663)

```c++

#include <bits/stdc++.h>

using namespace std;

int N, M;
bool selected[9];

vector<int> nums;
vector<int> selectedNum;
void search(int count){
    if(count == M){
        for(int i = 0; i < selectedNum.size(); i++){
            cout << selectedNum[i] << " ";
        }
        cout << "\n";
        return;
    }
    
    int prev = 0;
    for(int i = 0; i < N; i++){
        if(!selected[i] && prev != nums[i]){
            prev = nums[i];
            selected[i] = true;
            selectedNum.push_back(nums[i]);
            search(count + 1);
            selected[i] = false;
            selectedNum.pop_back();
        }
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        nums.push_back(input);
    }

    sort(nums.begin(), nums.end());

    search(0);

    return 0;
}
```