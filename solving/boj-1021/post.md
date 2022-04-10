[문제 바로가기](https://boj.kr/1021)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    int N, M;
    cin >> N >> M;

    deque<int> num;
    for(int i = 0; i < N; i++){
        num.push_back(i + 1);
    }

    int count = 0;
    for(int i = 0; i < M; i++){
        int target;
        cin >> target;

        int fromLeft, fromRight;
        for(int i = 0; i < num.size(); i++){
            if(num[i] == target){
                fromLeft = i;
                fromRight = num.size() - i;
                break;
            }
        }

        if(fromLeft <= fromRight){
            while(1){
                if(num.front() == target){
                    num.pop_front();
                    break;
                }
                
                num.push_back(num.front());
                num.pop_front();
                count++;
            }
        }else{
            while(1){
                if(num.back() == target){
                    num.pop_back();
                    count++;
                    break;
                }

                num.push_front(num.back());
                num.pop_back();
                count++;
            }
        }
    }

    cout << count;
}
```