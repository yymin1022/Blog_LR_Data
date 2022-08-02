[문제 바로가기](https://boj.kr/5430)

```c++
#include <bits/stdc++.h>

using namespace std;

deque<string> split(string, char);
 
int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    int T;
    cin >> T;

    for(int i = 0; i < T; i++){
        bool isError = false;
        bool isReversed = false;
        int N;
        string P, tempNum;
        cin >> P >> N >> tempNum;

        deque<string> nums = split(tempNum.substr(1, tempNum.size() - 2), ',');

        for(int j = 0; j < P.size(); j++){
            if(P[j] == 'D'){
                if(!nums.empty()){
                    if(isReversed){
                        nums.pop_back();
                    }else{
                        nums.pop_front();
                    }
                }else{
                    isError = true;
                    break;
                }
            }else if(P[j] == 'R'){
                isReversed ? isReversed = false : isReversed = true;
            }
        }

        if(!isError){
            cout << "[";
            if(!nums.empty()){
                while(1){
                    if(isReversed){
                        cout << nums.back();
                        nums.pop_back();
                    }else{
                        cout << nums.front();
                        nums.pop_front();
                    }                    
                    if(nums.empty()){
                        break;
                    }
                    cout << ",";
                }
            }
            
            cout << "]";
        }else{
            cout << "error";
        }
        cout << "\n";
    }

    return 0;
}

deque<string> split(string str, char cut) {
    deque<string> result;
    istringstream ss(str);
    string stringBuffer;

    while (getline(ss, stringBuffer, cut))
    {
        result.push_back(stringBuffer);
    }
 
    return result;
}```