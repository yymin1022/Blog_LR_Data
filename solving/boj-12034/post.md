[문제 바로가기](https://boj.kr/12034)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int i = 1; i <= T; i++){
        int N;
        cin >> N;

        vector<int> price;
        for(int j = 0; j < N * 2; j++){
            int input;
            cin >> input;
            price.push_back(input);
        }

        cout << "Case #" << i << ": ";
        for(int j = 0; j < N * 2; j++){
            for(int k = j + 1; k <N * 2; k++){
                if(price[k] / 4 * 3 == price[j]){
                    price[k] = -1;
                    cout << price[j] << " ";
                    break;
                }
            }
        }
        cout << "\n";
    }

    return 0;
}

```