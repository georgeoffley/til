# Using Tailwind In Non-React Projects

[Source](https://tailwindcss.com/docs/installation)

You can actually use tailwind in non-react projects. For example, just straight up HTML pages. Or even Svelte, maybe?

You install tailwind the same way as you would with React. However, you have to run the CLI tool along with whatever server you're using with the below command.

```bash
npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
```

What that does is take in the root CSS file in the argument after the `-i` flag, compiles the CSS, and drops the compiled CSS into the output file named after the `-o` flag. This CSS file is then imported into the project like a normal CSS file. 

#GeneralTools 
	#TailWindCss 
	#CSS 