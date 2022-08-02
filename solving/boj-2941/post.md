[문제 바로가기](https://boj.kr/2941)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    string input;
    cin >> input;

    int count = 0;
    for(int i = 0; i < input.size(); i++){
        if(input[i] == 'c'){
            if(i + 1 < input.size() && input[i + 1] == '='){
                count++;
                i++;
                continue;
            }else if(i + 1 < input.size() && input[i + 1] == '-'){
                count++;
                i++;
                continue;
            }
        }else if(input[i] == 'd'){
            if(i + 2 < input.size() && input[i + 1] == 'z' && input[i + 2] == '='){
                count++;
                i += 2;
                continue;
            }else if(i + 1 < input.size() && input[i + 1] == '-'){
                count++;
                i++;
                continue;
            }
        }else if(input[i] == 'l'){
            if(i + 1 < input.size() && input[i + 1] == 'j'){
                count++;
                i++;
                continue;
            }
        }else if(input[i] == 'n'){
            if(i + 1 < input.size() && input[i + 1] == 'j'){
                count++;
                i++;
                continue;
            }
        }else if(input[i] == 's'){
            if(i + 1 < input.size() && input[i + 1] == '='){
                count++;
                i++;
                continue;
            }
        }else if(input[i] == 'z'){
            if(i + 1 < input.size() && input[i + 1] == '='){
                count++;
                i++;
                continue;
            }
        }
        count++;
    }

    cout << count;

    return 0;
}```