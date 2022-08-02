[문제 바로가기](https://boj.kr/1264)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string input;
    getline(cin, input);

    while(input != "#"){
        int cnt = 0;
        for(int i = 0; i < input.size(); i++){
            if(input[i] == 'A' || input[i] == 'a'){
                cnt++;
            }else if(input[i] == 'E' || input[i] == 'e'){
                cnt++;
            }else if(input[i] == 'I' || input[i] == 'i'){
                cnt++;
            }else if(input[i] == 'O' || input[i] == 'o'){
                cnt++;
            }else if(input[i] == 'U' || input[i] == 'u'){
                cnt++;
            }
        }

        cout << cnt << "\n";

        getline(cin, input);
    }

    return 0;
}```