[문제 바로가기](https://boj.kr/16472)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int N;
    string word;
    cin >> N >> word;

    if(word.size() <= N){
        cout << word.size() << "\n";
        return 0;
    }

    int ans = 0;
    int cnt = 0;
    int left = 0;
    int right = 0;
    map<char, int> data;
    while(left <= right && right < word.size()){
        if(cnt <= N){
            if(data.find(word[right]) == data.end()){
                cnt++;
            }

            data[word[right]]++;
            right++;

            if(right == word.size() - 1 && cnt <= N){
                ans = max(right - left + 1, ans);
                break;
            }
        }else{
            data[word[left]]--;

            if(!data[word[left]]){
                cnt--;
                data.erase(word[left]);
            }

            left++;
        }

        if(cnt == N){
            ans = max(right - left, ans);
        }
    }

    cout << ans << "\n";

    return 0;
}```