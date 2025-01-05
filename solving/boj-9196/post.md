[문제 바로가기](https://boj.kr/9196)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    while(true){
        int h, w;
        cin >> h >> w;

        if(h == 0 && w == 0){
            break;
        }


        int ansD = 100 * 100 + 100 * 100;
        int ansH = 100;
        int ansW = 100;
        int maxD = h * h + w * w;
        for(int i = 1; i <= 150; i++){
            for(int j = i + 1; j <= 150; j++){
                int k = i * i + j * j;
                if(maxD > k || (maxD == k && h >= i)){
                    continue;
                }

                if(k < ansD || (k == ansD && i < ansH)){
                    ansD = k;
                    ansH = i;
                    ansW = j;
                }
                break;
            }

            if(i * i >= maxD){
                break;
            }
        }

        cout << ansH << " " << ansW << "\n";
    }

    return 0;
}
```