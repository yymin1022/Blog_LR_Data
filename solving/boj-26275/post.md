[문제 바로가기](https://boj.kr/26275)

```asm
global main
extern exit, printf

section .data
msg db "####################", 10, "##J1############J1##", 10, "#########J1#########", 10, "##J1############J1##", 10, "#########J1#########", 10, "#########J1#########", 10, "##J1############J1##", 10, "#########J1#########", 10, "##J1############J1##", 10, "####################", 0
section .text
main:
	push msg
	call printf

	mov dword [esp], 0
	call exit
```