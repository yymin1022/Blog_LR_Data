[문제 바로가기](https://boj.kr/4884)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long G, T, A, D;
	while(true){
        cin >> G >> T >> A >> D;

        if(G == -1 && T == -1 && A == -1 && D == -1){
            break;
        }

		long long limit = G * A + D;
		for(long i = 1; i < limit; i++){
			if(pow(2, i) == limit){
				break;
			}
			if(pow(2, i) > limit){
                limit = pow(2, i);
				break;
			}
		}

		long long X = (T * (T - 1) / 2) * G + limit - 1;
		long long Y = 0;
		if(D > 0){
            Y = limit - (G * A + D);
        }

        cout << G << "*" << A << "/" << T << "+" << D << "=" << X << "+" << Y << "\n";
	}

    return 0;
}
```