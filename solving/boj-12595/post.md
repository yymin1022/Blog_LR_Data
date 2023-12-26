[문제 바로가기](https://boj.kr/12595)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 1; i <= N; i++){
        int G;
        cin >> G;

        map<int, bool> arr;
        for(int j = 0; j < G; j++){
            int C;
            cin >> C;
            if(arr[C]){
                arr[C] = false;
            }else{
                arr[C] = true;
            }
        }

        cout << "Case #" << i << ": ";
        for(auto iter = arr.begin(); iter != arr.end(); iter++){
            if(iter->second){
                cout << iter->first << "\n";
            }
        }
    }

    return 0;
}
```