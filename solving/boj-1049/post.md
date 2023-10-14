[문제 바로가기](https://boj.kr/1049)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> sixPrice;
    vector<int> unitPrice;
    for(int i = 0; i < M; i++){
        int A, B;
        cin >> A >> B;
        sixPrice.push_back(A);
        unitPrice.push_back(B);
    }

    sort(sixPrice.begin(), sixPrice.end());
    sort(unitPrice.begin(), unitPrice.end());

    int ans = 0;
    int line = N;
    while(line > 0){
        if(line >= 6){
            if(sixPrice[0] > unitPrice[0] * 6){
                ans += unitPrice[0] * line;
                break;
            }else{
                ans += sixPrice[0];
                line -= 6;
            }
        }else{
            if(sixPrice[0] < unitPrice[0] * line){
                ans += sixPrice[0];
                line -= 6;
            }else{
                ans += unitPrice[0] * line;
                break;
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```