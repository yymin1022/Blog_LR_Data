[문제 바로가기](https://boj.kr/20366)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> snow;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        snow.push_back(input);
    }

    sort(snow.begin(), snow.end());

    int ans = 2147483647;
    for(int i = 0; i < N - 3; i++){
        for(int j = i + 3; j < N; j++){
            int from = i + 1;
            int to = j - 1;
            while(from < to){
                int anna = snow[i] + snow[j];
                int elsa = snow[from] + snow[to];

                int tmp = elsa - anna;
                ans = min(abs(tmp), ans);

                if(tmp > 0){
                    to--;
                }else{
                    from++;
                }
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```