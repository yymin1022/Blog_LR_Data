[문제 바로가기](https://boj.kr/25192)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int cnt = 0;
    set<string> chat;
    for(int i = 0; i < N; i++){
        string msg;
        cin >> msg;

        if(msg == "ENTER"){
            cnt += chat.size();
            chat.clear();
        }else{
            chat.insert(msg);
        }
    }

    cnt += chat.size();
    
    cout << cnt << "\n";

    return 0;
}```