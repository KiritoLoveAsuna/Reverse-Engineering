### Linux Syscall table
https://filippo.io/linux-syscall-table
### Assembly
```
mov esi, offset dword_80490E8
offset 的意思是：取变量的地址，而不是取变量里面的数据。
In C ,char *esi = &dword_80490E8;
ESI = 0x080490E8
```
```
mov eax, [esi]
[esi] 才表示：
去 ESI 指向的内存地址，把里面的数据取出来。
In C , eax = *(uint32_t *)esi;
```
