# Finding Files by Permission Types

[Docs Resource](https://man7.org/linux/man-pages/man1/find.1.html)

You can use the `find` command to find files by permissions.

This can be done using the following command.

```bash
find ./inhere/ \! -executable
```

The above command is looking to locate a file within the `./inhere` directory. 

The `\!` is a __NOT__ condition and the `-executable` is looking for the executable permission. So the above command is looking for a file in the `./inhere` directory and it should only find files that __DO NOT__ have the executable permission.

The `!` by itself is a not condition but the backslash (`\`) is an escape character.

In the above instance the fill command for the file I was looking for would have been something like `find ./inhere -size 1033c \! -executable -readable` since I was looking for a file that was human readable, not executable, and 1033 bytes in size.