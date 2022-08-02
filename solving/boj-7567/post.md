[문제 바로가기](https://boj.kr/7567)

```c++
#include <iostream>
#include <string>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int size = 0;;
    string input;
    cin >> input;

    for(int i = 0; i < input.size(); i++){
        if(i != 0){
            if(input[i] != input[i - 1]){
                size += 10;
            }else{
                size += 5;
            }
        }else{
            size += 10;
        }
    }

    cout << size;

    return 0;
}```