# Pretty Log Messages with Pino Pretty

[Source](https://github.com/pinojs/pino-pretty)

Pino pretty is a tool for cleaning up logging messages. For example if I am starting a task or API server you can see a cleaner version of the logs. 

I had to install it using the global flag to avoid putting it in my current project. I was able to install using `npm install pino-pretty -g`

You use the tool buy appending any command with ` | pino-pretty`. With a space, a pipe, and an additional space. So like:

```bash
pnpm api | pino-pretty
```