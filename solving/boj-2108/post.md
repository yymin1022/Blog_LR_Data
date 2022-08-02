[문제 바로가기](https://boj.kr/2108)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int sum = 0;
    vector<int> cnt(8001, 0);
    vector<int> nums;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        cnt[input + 4000]++;
        nums.push_back(input);
        sum += input;
    }

    sort(nums.begin(), nums.end());

    bool mostFound = false;
    int avg = round((float)sum / N);
    int center = nums[N / 2];
    int mostCount = -5000;
    int mostValue = 0;
    int range = nums.back() - nums.front();

    for(int i = 0; i < 8001; i++){
        if(cnt[i] == mostCount){
            if(mostFound){
                mostCount = cnt[i];
                mostFound = false;
                mostValue = i - 4000;
            }
        }else if(cnt[i] > mostCount){
            mostCount = cnt[i];
            mostFound = true;
            mostValue = i - 4000;
        }
    }

    cout << avg << "\n";
    cout << center << "\n";
    cout << mostValue << "\n";
    cout << range << "\n";

    return 0;
}```