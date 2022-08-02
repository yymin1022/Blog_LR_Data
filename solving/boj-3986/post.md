[문제 바로가기](https://boj.kr/3986)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    int N;
    cin >> N;

    int count = 0;
    for(int i = 0; i < N; i++){
        stack<char> wordStack;
        string word;
        cin >> word;

        for(int j = 0; j < word.size(); j++){
            if(wordStack.empty() || wordStack.top() != word[j]){
                wordStack.push(word[j]);
            }else{
                wordStack.pop();
            }
        }

        if(wordStack.empty()){
            count++;
        }
    }

    cout << count << "\n";
}```