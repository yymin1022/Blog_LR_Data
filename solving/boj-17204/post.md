[문제 바로가기](https://boj.kr/17204)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[151];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    int ans = 0;
    int cur = 0;
    while(true){
        if(cur == M){
            cout << ans << "\n";
            return 0;
        }

        int next = arr[cur];
        if(!isVisit[next]){
            ans++;
            cur = next;
            isVisit[next] = true;
        }else{
            break;
        }
    }

    cout << -1 << "\n";

    return 0;
}#include <bits/stdc++.h>

using namespace std;

bool isVisit[151];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    int ans = 0;
    int cur = 0;
    while(true){
        if(cur == M){
            cout << ans << "\n";
            return 0;
        }

        int next = arr[cur];
        if(!isVisit[next]){
            ans++;
            cur = next;
            isVisit[next] = true;
        }else{
            break;
        }
    }

    cout << -1 << "\n";

    return 0;
}
```
