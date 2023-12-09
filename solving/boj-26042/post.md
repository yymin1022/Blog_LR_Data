[문제 바로가기](https://boj.kr/26042)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    pair<int, int> ans = make_pair(0, 100001);
    queue<int> q;
    while(N--){
        int type, num;
        cin >> type;

        if(type == 1){
            cin >> num;
            q.push(num);
            if((ans.first < q.size()) || (ans.first == q.size() && ans.second > num)){
                ans = make_pair(q.size(), num);
            }
        }else{
            q.pop();
        }
    }

    cout << ans.first << " ";
    cout << ans.second << "\n";

    return 0;
}
```