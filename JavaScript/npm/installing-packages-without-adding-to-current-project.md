# Installing Packages Without Adding Them to a Current Project

[Source](https://docs.npmjs.com/cli/v6/commands/npm-install)

When you install something via npm the default behavior is for npm to add the package to the `package.json` of your current project which is under the `node_modules` folder. 

You can avoid this by appending a `-g` to the end of the install command. So for example:

```bash
npm install pino-pretty -g
```

#JavaScript
	#npm