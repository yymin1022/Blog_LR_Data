[문제 바로가기](https://boj.kr/5575)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    for(int i = 0; i < 3; i++){
        int h1, h2, m1, m2, s1, s2;
        cin >> h1 >> m1 >> s1 >> h2 >> m2 >> s2;

        h2 -= h1;
        m2 -= m1;
        s2 -= s1;

        if(s2 < 0){
            m2--;
            s2 += 60;
        }
        if(m2 < 0){
            h2--;
            m2 += 60;
        }

        cout << h2 << " " << m2 << " " << s2 << "\n";
    }

    return 0;
}
```