[문제 바로가기](https://boj.kr/17219)

```c++
#include <iostream>
#include <map>
#include <string>

using namespace std;

int main(){
    cin.tie(NULL);
    ios::sync_with_stdio(false);

    map <string, string> sitePW;
    int N, M;

    cin >> N >> M;

    for(int i = 0; i < N; i++){
        string URL, PW;

        cin >> URL >> PW;
        sitePW.insert(make_pair(URL, PW));
    }

    for(int i = 0; i < M; i++){
        string input;
        
        cin >> input;
        cout << sitePW[input] << "\n";
    }

    return 0;
}
```