[문제 바로가기](https://boj.kr/10156)

```c++
#include <iostream>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int val, num, cur;

    cin >> val >> num >> cur;

    int result = val * num - cur;

    if(result > 0){
        cout << result;
    }else{
        cout << 0;
    }


    return 0;
}```