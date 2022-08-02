[문제 바로가기](https://boj.kr/10816)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> cards;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        cards.push_back(input);
    }

    sort(cards.begin(), cards.end());

    int M;
    cin >> M;
    
    for(int i = 0; i < M; i++){
        int input;
        cin >> input;

        int value = upper_bound(cards.begin(), cards.end(), input) - lower_bound(cards.begin(), cards.end(), input);

        cout << value << " ";
    }
    
    return 0;
}```