[문제 바로가기](https://boj.kr/11655)

```c++
#include <iostream>
#include <queue>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S;
    getline(cin, S);

    for(char c: S){
        if(c >= 'A' && c <= 'M'){
            c += 13;
        }else if(c >= 'N' && c <= 'Z'){
            c -= 13;
        }else if(c >= 'a' && c <= 'm'){
            c += 13;
        }else if(c >= 'n' && c <= 'z'){
            c -= 13;
        }

        cout << c;
    }

    return 0;
}
```