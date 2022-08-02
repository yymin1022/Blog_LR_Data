[문제 바로가기](https://boj.kr/1339)

```c++
#include <algorithm>
#include <cmath>
#include <iostream>
#include <string>
#include <vector>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    vector<int> charCount;
    for(int i = 0; i < 26; i++){
        charCount.push_back(0);
    }

    int num;
    cin >> num;

    for(int i = 0; i < num; i++){
        string input;
        cin >> input;

        int size = input.size();
        int offset = pow(10, size - 1);

        for(int j = 0; j < size; j++, offset /= 10){
            int ascii = (int)input[j] - 65;
            charCount[ascii] += offset;
        }
    }

    int result = 0;
    int offset = 9;

    while(count(charCount.begin(), charCount.end(), 0) < 26){
        int max = 0;

        for(int i = 0; i < 26; i++){
            if(charCount[i] > charCount[max]){
                max = i;
            }
        }

        result += offset * charCount[max];

        charCount[max] = 0;
        offset--;
    }

    cout << result;

    return 0;
}```