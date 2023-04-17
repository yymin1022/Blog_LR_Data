[문제 바로가기](https://boj.kr/1484)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int G;
    cin >> G;

    int left = 1;
    int right = 1;
    vector<int> ans;
    while(left <= right && right <= 100001){
        int tmpG = right * right - left * left;

        if(tmpG == G){
            ans.push_back(right);
            right++;
        }else if(tmpG < G){
            right++;
        }else{
            left++;
        }
    }

    if(!ans.size()){
        cout << -1 << "\n";
    }else{
        for(int tmp : ans){
            cout << tmp << "\n";
        }
    }

    return 0;
}
```