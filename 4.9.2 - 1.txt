.386
.model flat, stdcall
.stack 4096
ExitProcess proto, dwExitCode:dword

.data
; p. 136 Algorithm workbench, ex. 1 - Write a sequence of MOV instructions that will exchange the upper and lower words in a
doubleword variable named three.
three dword 12345678h
three1 word 2 dup(0)

.code
main PROC

mov ax, word ptr three
mov three1 + 2, ax
mov ax, word ptr three + 2
mov three1, ax
mov eax, dword ptr three1

invoke ExitProcess,0
main endp
end main