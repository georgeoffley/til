# Finding Text Inside a Text File

[Docs Resource](https://man7.org/linux/man-pages/man1/grep.1.html)

I was searching for text that was next to the words "millionth" in a text file. 

I was able to do this by using the command below.

```bash
grep "millionth*" ./data.txt
```

I used the text pattern `"millionth*"` to find the next words in that line and then passed in the file to look into it.