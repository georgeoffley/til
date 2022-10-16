# Checking Website Latency and Recording it

[Docs](https://curl.se/docs/manpage.html)

I learned this doing an interview. The goal was to create a quick task to call a webserver and get the latency time. I chose to use curl as the goal was to get it using HTTP.

## Command

```bash
COMMAND=$(curl -w "%{time_total}" -o ./ -s "https://google.com")
```

`COMMAND` is the saved variable for the bash script.

The `-w` is for writing the output. You can use the `@` to use a file to serve as the template, which is what I originally did. However, I was able to just get the stdout to show the time using `"%{time_total}"`. Variables are specified using the `%{}` syntax.

The `time_total` is an available variable of a list of variables which you can grab from a curl call. It represents the total time the operation took.