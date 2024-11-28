[문제 바로가기](https://boj.kr/14721)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> arr;
    for(int i = 0; i < N; i++){
        int A, B;
        cin >> A >> B;
        arr.push_back(make_pair(A, B));
    }

    long min = 987654321;
    int ans[2] = {0, 0};
    for(int a = 1; a <= 100; a++){
        for(int b = 1; b <= 100; b++){
            long rss = 0;
            for(int i = 0; i < N; i++){
                long cur = arr[i].first * a + b - arr[i].second;
                rss += cur * cur;
            }

            if(min>rss){
                min = rss;
                ans[0] = a;
                ans[1] = b;
            }
        }
    }

    cout << ans[0] << " ";
    cout << ans[1] << "\n";

    return 0;
}
```