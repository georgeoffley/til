# Referencing Dashed File Name in Bash

[SO Resource](https://stackoverflow.com/questions/42187323/how-to-open-a-dashed-filename-using-terminal)

So the problem was that we needed to access a file named `-`. If we just tried `cat -` we would get an error as bash is interpreting the dash (`-`) as a flag.

If you want to perform file operations on this file you need to tell bash that it is a file instead of leaving it to bash to interoperate. You do that by doing this: `cat ./-`.

So using the `./` to indicate that we're looking in the current directory will let you perform file operations on that file. 

#bash