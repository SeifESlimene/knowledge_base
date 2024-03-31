# ==Useful Debug Commands==

---

##### Debugging C:
> `$ gcc -g -o fact fact.c`

- gdb fact
- list
- break main or break 4
- run or r
- next or n
- info local
- print i or p i
- q or quit

---

##### Debugging Shell Script:
> `$ bash -x ./hello.sh`

Or

in `hello.sh`
```shell
set -x
set +x
```

---

##### Debugging In Ruby:

```ruby
binding.pry
```

Or

```ruby
console
```

Or

```ruby
prybug
```

---

##### Debugging In Python
```python
import pdb; pdb.set_trace()
```

---

- Debug an executable:
> `$ gdb {{executable}}`

- Attach a process to gdb:
> `$ gdb -p {{procID}}`

- Debug with a core file:
> `$ gdb -c {{core}} {{executable}}`

- Execute given GDB commands upon start:
> `$ gdb -ex "{{commands}}" {{executable}}`

- Start gdb and pass arguments to the executable:
> `$ gdb --args {{executable}} {{argument1}} {{argument2}}`
