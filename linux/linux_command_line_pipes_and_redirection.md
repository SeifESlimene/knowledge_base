> `$ sleep 60 &`

> `$ sudo lsof -p $!`

> `$ tty`

##### default fds:
`0` stdin
`1` stdout
`2` stderr

##### run program1, stdout/stderr to terminal (default):
> `$ program1`

##### send stdout from program1 to stdin of program2 with anonymous pipe:
> `$ program1 | program2`

##### We can chain pipes:
> `$ ls -l | grep write | wc -l`

##### run program1, stdout to out.log, stderr to terminal:
> `$ program1 1> out.log`

> `$ program1 > out.log`

##### run program1, stdout/stderr to out.log, nothing to terminal:
> `$ program1 1> out.log 2> out.log`

> `$ program1 > out.log 2> out.log`

> `$ program1 > out.log 2>&1`


==PS==: `>&` is the syntax to redirect a stream to another file descriptor - `0` is stdin, `1` is stdout, and `2` is stderr.

##### run program1 with input.txt as input,
##### stdout/stderr to terminal:
> `$ program1 < input.txt`

> `$ cat input.txt | program1`

##### run program1 with input.txt to stdin,
##### stdout to output.txt, stderr to terminal:
> `$ program1 < input.txt > output.txt`

> `$ cat input.txt | program1 > output.txt`

##### send stdout from program1 to stdin of program2 with named pipe:
> `$ mkfifo mypipe`

> `$ program1 > mypipe`

> `$ program2 < mypipe`

##### run program1, discard all output:
> `$ program1 > /dev/null 2>&1`

##### run program1, send fd4 to out.log (see write.c):
> `$ ./write 4> out.log`

##### write.c:
```c
#include <unistd.h>

int main(void) {
  write(4, "hello\n", 6)
}
```

==PS==: use `>>` instead of `>` to append
