## $#:
##### ./test:
```bash
#! /bin/bash
echo $#
```
##### Command:
> `$ ./test 1 2 3`
##### Output:
`3`
##### Explanation
`$#` = number of arguments.

---

## $@:
##### ./test:
```bash
#! /bin/bash
echo $@
```
##### Command:
> `$ ./test 1 2 3`
##### Output:
`1 2 3`
##### Explanation
`$@` = what parameters were passed.

---

## $?:
##### ./test:
```bash
#! /bin/bash
echo $?
```
##### Command:
> `$ ./test 1 2 3`
##### Output:
`0`
##### Explanation
`$?` = was last command successful. Answer is 0 which means ==yes==

---

## $*:
##### ./test:
```bash
#! /bin/bash
echo $*
```
##### Command:
> `$ ./test param1 param2 param3`
##### Output:
`param1 param2 param3`
##### Explanation
`$*` = expand positional parameters.

---

## $$:
##### ./test:
```bash
#! /bin/bash
echo $$
```
##### Command:
> `$ ./test`
##### Output:
`6360`
##### Explanation
`$$` = PID of current shell.

---

## $!:
##### ./test:
```bash
#! /bin/bash
sleep 60 &
echo $!
```
##### Command:
> `$ ./test`
##### Output:
`8047`
##### Explanation
`$!` = Most recent job placed in background.

---

## $0:
##### ./test:
```bash
#! /bin/bash
echo $0
```
##### Command:
> `$ ./test`
##### Output:
`./test`
##### Explanation
`$0` = Shell script name.

---

## $_:
##### ./test:
```bash
#! /bin/bash
echo $_
```
##### Command:
> `$ ./test`
##### Output:
`./test`
##### Explanation
`$_` = Last argument passed on to your previous command.

---

## $-:
##### ./test:
```bash
#! /bin/bash
echo $-
```
##### Command:
> `$ ./test`
##### Output:
`himBH`
##### Explanation
- H - histexpand
- m - monitor
- h - hashall
- B - braceexpand
- i - interactive

---

==PS==: `$*` and `$@` are special bash parameters and if used without double quotes then both will behave identical.
But if you double quotes then they will behave differently, in the case of `$*` individual parameters will be separated by first char of `IFS` characters while in case of $@ individual parameters will appear in quotes and separated by space.
