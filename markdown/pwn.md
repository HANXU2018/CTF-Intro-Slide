# Pwn
二进制漏洞利用


## 前置技能
- Reverse
- OS
- C/C++


## 二级分类
- Linux
    - 栈
    - 堆
    - 内核
    - 异构
- Windows
    - 栈


## 通用
- 内存布局
- 整数溢出
- 格式化字符串
- 目的
    - 泄露关键地址
    - 任意/部分地址读
    - 任意/部分地址写
    - 劫持控制流


## 栈利用
- 函数调用栈原理
- ROP系列
    - ret2text
    - ret2shellcode
    - ret2syscall
    - ret2libc
    - ret2csu
    - ret2dl_runtime_resolve
    - ret2VDSO
    - SROP
    - BROP


- 技巧
    - 栈迁移
    - partial overwrite
    - stack smash
- 防护措施
    - NX/DEP
    - Canary
    - PIE/ASLR
    - RELRO


## 堆利用
- GLibc堆基础
- 堆风水
- 堆溢出
- uaf
- double free
- off-by-one
- unlink
- 堆块重叠
- fastbin attack
- unsortedbin attack
- largebin attack
- <span class="fragment highlight-blue">**tcache相关(glibc >= 2.26)**</span>
- <span class="fragment highlight-blue">**House of系列**</span>


## 其它
- 内核利用
- `IO_FILE`利用
- 异构
- Unicorn


## 常用工具
- Reverse中的工具
- gdb插件
    - peda/pwndbg/gef
    - <span class="fragment highlight-blue">**pwngdb**</span>
- 框架
    - pwntools
    - welpwn
- ROP相关
    - ROPgadgets
    - ropper


- GLibC相关
    - LibcSearcher
    - libc-database
    - glibc-all-in-one
    - libc-2.23 (Ubuntu 16)
    - libc-2.27 (Ubuntu 18)
    - libc-2.29 (Ubuntu 19)
    - onegadget
    - `ldd`
    - patchelf