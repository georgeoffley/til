# Finding Files by Size

[Doc Resource](https://man7.org/linux/man-pages/man1/find.1.html#OPTIONS)

```bash
find ./inhere -size 1033c \! -executable
```

The above command uses the `-size` option for find and then looks for a file 1033 bytes in size.

__Important to remember the `c` is what indicates bytes. Not `b`, as that indicates 512-byte blocks.__

#bash