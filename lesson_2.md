# 2. Выход из программы

```assembly
SECTION .data
msg     db      'Hello, World!', 0Ah
 
SECTION .text
global  _start
 
_start:
 
 mov	eax, 4
 mov	ebx, 1
 mov	ecx, msg
 mov	edx, 14
 int 80h

 mov	eax, 1 ; Вызов sys_exit
 mov	ebx, 0 ; количество ошибок в ebx
 int 80h
 ```
 
 Для того, чтобы выйти из программы корректно (а не получить ошибку Segmentation Fault), нужно выполнить системное прерывание sys_exit