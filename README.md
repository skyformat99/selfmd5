# selfmd5
计算自身md5的最小程序，最终大小约748字节.
```
# ll selfmd5 
-rwxr-xr-x 1 root root 748 4月   9 09:52 selfmd5
```

# 编译
* 先写c，然后编译成汇编
```
gcc -S  main-src.c md5-src.c -fno-asynchronous-unwind-tables -Os -ffast-math -fomit-frame-pointer -fsingle-precision-constant -fno-verbose-asm
```
* 然后把main.s的依赖libc的部分干掉，换成直接syscall
* 精简两个.s的无用代码，编译，并sstrip
```
./build-asm.sh
```
