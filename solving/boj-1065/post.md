[문제 바로가기](https://boj.kr/1065)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isHansoo(int num){
    int num1 = num / 100;
    int num2 = num % 100 / 10;
    int num3 = num % 10;

    if(num1 - num2 == num2 - num3){
        return true;
    }
    
    return false;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    int N;
    cin >> N;

    int count = 0;
    for(int i = 1; i <= N; i++){
        if(i < 100){
            count++;
        }else if(i < 1000 && isHansoo(i)){
            count++;
        }
    }

    cout << count;
}```