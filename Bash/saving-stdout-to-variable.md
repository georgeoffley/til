# Saving Stdout As a Variable in Bash

[SO Resource](https://stackoverflow.com/questions/27472540/difference-between-and-in-bash)

You have to use `$()` which is an expression for command and tells bash to take this command and put the output in this place.

`COMAND=$(curl -w "%{time_total}" -o ./ -s "https://google.com")`

So the above will run the curl command, take the output of that command, and save it to the `COMMAND` variable. 

That variable is accessed using this syntax: `${COMMAND}`.