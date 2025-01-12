[문제 바로가기](https://boj.kr/5073)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int arr[3];
    while(true){
        cin >> arr[0] >> arr[1] >> arr[2];

        if(arr[0] == 0 && arr[1] == 0 && arr[2] == 0){
            break;
        }

        sort(arr, arr + 3);

        if(arr[0] + arr[1] <= arr[2]){
            cout << "Invalid" << "\n";
        }else if(arr[0] == arr[1] && arr[0] == arr[2]){
            cout << "Equilateral" << "\n";
        }else if(arr[0] != arr[1] && arr[0] != arr[2] && arr[1] != arr[2]){
            cout << "Scalene" << "\n";
        }else{
            cout << "Isosceles" << "\n";
        }
    }

    return 0;
}
```