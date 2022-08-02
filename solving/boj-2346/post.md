[문제 바로가기](https://boj.kr/2346)

```c++
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;
 
int main(){
    int N;
    cin >> N;
 
    vector<pair<int, int>> balloon;
 
    for(int i = 1; i <= N; i++){
        int input;
        cin >> input;
        balloon.push_back(make_pair(i, input));
    }
 
    while(!balloon.empty()){
        cout << balloon.front().first << " ";
        int num = balloon.front().second;
        balloon.erase(balloon.begin());
 
        if(balloon.empty()){
            return 0;
        }
 
        if(num > 0){
            for(int i = 0; i < num - 1; i++){
                balloon.push_back(balloon.front());
                balloon.erase(balloon.begin());
            }
        }else{
            for(int i = 0; i > num; i--){
                balloon.insert(balloon.begin(), balloon.back());
                balloon.erase(balloon.end()-1);
            }
        }
    }
 
}```