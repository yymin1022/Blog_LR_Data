[문제 바로가기](https://boj.kr/2309)

```c++
#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int heightSum = 0;
    vector<int> mans;

    for(int i = 0; i < 9; i++){
        int num;
        cin >> num;
        heightSum += num;
        mans.push_back(num);
    }

    heightSum -= 100;
    sort(mans.begin(), mans.end());

    for(int i = 0; i < 9; i++){
        for(int j = 0; j < 9; j++){
            if(mans[i] + mans[j] == heightSum){
                for(int k = 0; k < 9; k++){
                    if(k != i && k != j){
                        cout << mans[k] << "\n";
                    }
                }

                return 0;
            }
        }
    }

    return 0;
}
```