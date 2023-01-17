# Unix Terminal Profile Changes

---
## Docs and Source
[Source Here](https://linuxtect.com/zsh-profile-file-profile-zprofile-zshrc/)

---
## Explanation and Notes
The terminal in Unix (Linux, Macs) has the ability to run scripts for changes in your terminal setup.

There are different terminal types, but Macs have zsh already going, so I’ve used that.

Setting up your profile is done by editing the `~/.zshrc` file. Which is just a script on which you can run commands.

For example, I’ve used it to set some needed configuration scripts into my $PATH so that I can run them like regular commands.

```bash
if [ -f ~/Dev/environment-deps/deps.sh ]; then
  . ~/Dev/environment-deps/deps.sh
fi
```

The above is a script that looks for a specific setup file in my file directory and, if it finds it, executes that script. That script runs a bunch of bash commands and gives me custom commands I can run to get work done locally.

This can be expanded to whatever you want since it is all bash code.

---


#Unix
	#Terminal