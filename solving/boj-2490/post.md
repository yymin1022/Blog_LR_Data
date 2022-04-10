[문제 바로가기](https://boj.kr/2490)

```c++
#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    for(int i = 0; i < 3; i++){
        int count = 0;
        for(int j = 0; j < 4; j++){
            int input;
            cin >> input;

            if(input == 1){
                count++;
            }
        }

        if(count == 0){
            cout << "D" << "\n";
        }else if(count == 1){
            cout << "C" << "\n";
        }else if(count == 2){
            cout << "B" << "\n";
        }else if(count == 3){
            cout << "A" << "\n";
        }else if(count == 4){
            cout << "E" << "\n";
        }
    }

    return 0;
}
```