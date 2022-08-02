[문제 바로가기](https://boj.kr/24393)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    queue<int> mainDeque;
    queue<int> leftDeque;
    queue<int> rightDeque;

    mainDeque.push(1);
    for(int i = 1; i < 27; i++){
        mainDeque.push(0);
    }

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        int count = 0;
        int sum = 0;

        for(int j = 0; j < 13; j++){
            leftDeque.push(mainDeque.front());
            mainDeque.pop();
        }
        for(int j = 0; j < 14; j++){
            rightDeque.push(mainDeque.front());
            mainDeque.pop();
        }

        while(sum < 27){
            int num;
            cin >> num;

            count++;
            sum += num;

            if(count % 2){
                for(int j = 0; j < num; j++){
                    mainDeque.push(rightDeque.front());
                    rightDeque.pop();
                }
            }else{
                for(int j = 0; j < num; j++){
                    mainDeque.push(leftDeque.front());
                    leftDeque.pop();
                }
            }
        }
    }

    for(int i = 0; i < 27; i++){
        if(mainDeque.front()){
            cout << i + 1;
            break;
        }else{
            mainDeque.pop();
        }
    }
}```