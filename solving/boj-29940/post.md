[문제 바로가기](https://boj.kr/29940)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, S;
    cin >> N >> S;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    int ans = 0;
    int fromL = 0;
    int fromR = N - 1;
    while(fromL < fromR){
        int sum = arr[fromL] + arr[fromR];

        if(sum == S){
            ans++;
        }

        if(sum > S){
            fromR--;
        }else{
            fromL++;
        }
    }

    cout << ans << "\n";

    return 0;
}

```
