[문제 바로가기](https://boj.kr/2501)

```c++
#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int count = 0;
    int n, k;
    vector<int> nums;
    cin >> n >> k;

    for(int i = 1; i < n; i++){
        if(!(n % i)){
            count++;

            if(count == k){
                cout << i;
                return 0;
            }
        }
    }

    cout << 0;

    return 0;
}```