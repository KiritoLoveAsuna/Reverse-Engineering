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
```
mov   [edx], 2334h
│     │      │
│     │      └── 源操作数：立即数 0x2334
│     └── 目标操作数：内存，地址由 EDX 的值给出
└── 传送指令：把右边的东西复制到左边

mov [edx], 2334h 的意思是：

把十六进制立即数 2334h 写入 EDX 寄存器所指向的那个内存单元。

拆开看：

```asm
mov   [edx], 2334h
│     │      │
│     │      └── 源操作数：立即数 0x2334
│     └── 目标操作数：内存，地址由 EDX 的值给出
└── 传送指令：把右边的东西复制到左边

等价于 C 语言类似：  
*(uint16_t*)edx = 0x2334; 
```

 
