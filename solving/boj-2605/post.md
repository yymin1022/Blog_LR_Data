[문제 바로가기](https://boj.kr/2605)

```c++
#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int num;
    vector<int> command;
    vector<int> student;
    vector<int> temp;

    cin >> num;

    for(int i = 0; i < num; i++){
        int input;
        cin >> input;
        command.push_back(input);
        student.push_back(i + 1);
    }

    for(int i = 0; i < num; i++){
        for(int j = command[i]; j < i; j++){
            int temp = student[i];
            student[i] = student[j];
            student[j] = temp;
        }
    }

    reverse(student.begin(), student.end());

    for(int i = 0; i < num; i++){
        cout << student[i] << " ";
    }

    return 0;
}```