[문제 바로가기](https://boj.kr/13144)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool isVisit[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    long long cnt = 0;
    int left = 0;
    int right = 0;
    while(left < N){
        while(right < N && !isVisit[arr[right]]){
            isVisit[arr[right]] = true;
            right++;
        }

        cnt += right - left;
        isVisit[arr[left]] = false;
        left++;
    }

    cout << cnt << "\n";
    
    return 0;
}
```