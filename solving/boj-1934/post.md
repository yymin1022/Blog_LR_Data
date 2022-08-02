[문제 바로가기](https://boj.kr/1934)

```c++
#include <bits/stdc++.h>

using namespace std;

int gcd(int, int);

int main(void){
    cin.tie(NULL);
    cout.tie(NULL);
	ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int i = 0; i < T; i++){
        int A, B;
        cin >> A >> B;

        cout << (A * B) / gcd(A, B) << "\n";
    }

	return 0;
}

int gcd(int a, int b){
    while(b != 0){
        int temp = a % b;
        a = b;
        b = temp;
    }

    return a;
}```