[문제 바로가기](https://boj.kr/18115)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    int N;

    cin >> N;

    deque<int> cards;
    vector<int> A;

    for(int i = 0; i < N; i++){
        int command;
        cin >> command;
        A.push_back(command);
    }

    reverse(A.begin(), A.end());

    for(int i = 1; i <= N; i++){
        if(A[i - 1] == 1){
            cards.push_front(i);
        }else if(A[i - 1] == 2){
            int temp = cards.front();
            cards.pop_front();
            cards.push_front(i);
            cards.push_front(temp);
        }else{
            cards.push_back(i);
        }
    }

    while(!cards.empty()){
        cout << cards.front() << " ";
        cards.pop_front();
    }
}
```