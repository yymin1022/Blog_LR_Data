[문제 바로가기](https://boj.kr/28279)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    deque<int> dq;
    for(int i = 0; i < N; i++){
        int cmd, X;
        cin >> cmd;

        switch(cmd){
            case 1:
                cin >> X;
                dq.push_front(X);
                break;
            case 2:
                cin >> X;
                dq.push_back(X);
                break;
            case 3:
                if(dq.empty()){
                    cout << -1 << "\n";
                }else{
                    cout << dq.front() << "\n";
                    dq.pop_front();
                }
                break;
            case 4:
                if(dq.empty()){
                    cout << -1 << "\n";
                }else{
                    cout << dq.back() << "\n";
                    dq.pop_back();
                }
                break;
            case 5:
                cout << dq.size() << "\n";
                break;
            case 6:
                cout << (dq.empty() ? 1 : 0) << "\n";
                break;
            case 7:
                cout << (dq.empty() ? -1 : dq.front()) << "\n";
                break;
            case 8:
                cout << (dq.empty() ? -1 : dq.back()) << "\n";
                break;
        }
    }

    return 0;
}
```