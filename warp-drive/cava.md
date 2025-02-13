```warp-runnable-command
cava: error while loading shared libraries: libiniparser.so.1: cannot open shared object file: No such file or directory
Traceback (most recent call last):
  File "/home/o0xwolf/.config/bspwm/themes/Japanese Street 2/polybar/scripts/cava", line 12, in <module>
    cava_input = input().strip().split()
                 ^^^^^^^
EOFError: EOF when reading a line
```
### Resolve
```warp-runnable-command
sudo ln -s /usr/lib/libiniparser.<version>/usr/lib/libiniparser.so.1
sudo ln -s /usr/lib/libiniparser.so.4.2.4 /usr/lib/libiniparser.so.1
```
