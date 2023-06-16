[문제 바로가기](https://boj.kr/2947)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    vector<int> arr;
    for(int i = 0; i < 5; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    bool flag = false;
    while(!flag){
        flag = true;
        for(int i = 1; i < 5; i++){
            if(arr[i] < arr[i - 1]){
                flag = false;
                int tmp = arr[i];
                arr[i] = arr[i - 1];
                arr[i - 1] = tmp;

                for(int j = 0; j < 5; j++){
                    cout << arr[j] << " ";
                }

                cout << "\n";
            }
        }
    }

    return 0;
}
```