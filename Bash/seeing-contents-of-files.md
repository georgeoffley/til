# See Contents of Files in Bash

[Source](https://linuxhint.com/cat-command-bash/#:~:text=The%20%E2%80%9Ccat%E2%80%9D%20command%20in%20Bash%20stands%20for%20%E2%80%9Cconcatenate%E2%80%9D,and%20appending%20files%20in%20Linux.)

Run the `cat` command to see the contents of files. So for example:

```bash
cat ~/.gnupg/gpg.conf
```

You can also use this to create and append stuff to files.

__Create new file__
```bash
cat >filename.txt
```

__Append to file__
```bash
cat some text >> sampleTxt.txt
```

#bash