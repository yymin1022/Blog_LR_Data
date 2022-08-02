[문제 바로가기](https://boj.kr/5086)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(void){
    cin.tie(NULL);
    cout.tie(NULL);
	ios_base::sync_with_stdio(false);

    int a, b;
    cin >> a >> b;
    while(a != 0 && b != 0){
        if(a < b && b % a == 0){
            cout << "factor" << "\n";
        }else if(a > b && a % b == 0){
            cout << "multiple" << "\n";
        }else{
            cout << "neither" << "\n";
        }

        cin >> a >> b;
    }

	return 0;
}```