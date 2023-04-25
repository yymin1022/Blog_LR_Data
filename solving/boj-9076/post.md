[문제 바로가기](https://boj.kr/9076)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        vector<int> arr;
        for(int i = 0; i < 5; i++){
            int input;
            cin >> input;
            arr.push_back(input);
        }

        sort(arr.begin(), arr.end());

        if(arr[3] - arr[1] >= 4){
            cout << "KIN" << "\n";
        }else{
            cout << arr[1] + arr[2] + arr[3] << "\n";
        }
    }

    return 0;
}
```