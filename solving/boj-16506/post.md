[문제 바로가기](https://boj.kr/16506)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    map<string, string> assembly;
    assembly["ADD"] = "00000";
    assembly["ADDC"] = "00001";
    assembly["SUB"] = "00010";
    assembly["SUBC"] = "00011";
    assembly["MOV"] = "00100";
    assembly["MOVC"] = "00101";
    assembly["AND"] = "00110";
    assembly["ANDC"] = "00111";
    assembly["OR"] = "01000";
    assembly["ORC"] = "01001";
    assembly["NOT"] = "01010";
    assembly["MULT"] = "01100";
    assembly["MULTC"] = "01101";
    assembly["LSFTL"] = "01110";
    assembly["LSFTLC"] = "01111";
    assembly["LSFTR"] = "10000";
    assembly["LSFTRC"] = "10001";
    assembly["ASFTR"] = "10010";
    assembly["ASFTRC"] = "10011";
    assembly["RL"] = "10100";
    assembly["RLC"] = "10101";
    assembly["RR"] = "10110";
    assembly["RRC"] = "10111";

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        string cmd;
        int rD, rA, rB;
        cin >> cmd >> rD >> rA >> rB;

        string ans = "";
        ans += assembly[cmd];
        ans += "0";
        ans += bitset<3>(rD).to_string();
        ans += bitset<3>(rA).to_string();

        if(cmd[cmd.size() - 1] == 'C'){
            ans += bitset<4>(rB).to_string();
        }else{
            ans += bitset<3>(rB).to_string();
            ans += "0";
        }

        cout << ans << "\n";
    }

    return 0;
}
```