[문제 바로가기](https://boj.kr/13417)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        vector<char> arr;
        for(int i = 0; i < N; i++){
            char input;
            cin >> input;
            arr.push_back(input);
        }

        deque<char> res;
        res.push_back(arr[0]);

        for(int i = 1; i < N; i++){
            if(arr[i] <= res.front()){
                res.push_front(arr[i]);
            }else{
                res.push_back(arr[i]);
            }
        }

        for(auto iter = res.begin(); iter != res.end(); iter++){
            cout << *iter;
        }

        cout << "\n";
    }

    return 0;
}
```