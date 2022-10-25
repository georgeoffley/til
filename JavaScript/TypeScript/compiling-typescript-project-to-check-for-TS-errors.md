# Compiling TypeScript Project To Check For TS Errors

[Source](https://www.typescriptlang.org/docs/handbook/compiler-options.html)

When working in a TypeScript project, one useful tool is running the `tsc` command. 

```bash
tsc
```

Running this command locally will compile the closest project defined by the `tsconfig.json` file. You can also compile a set of TypScript files by passing in a glob of the files you want. 

```bash
# Run a compile based on a backwards look through the fs for a tsconfig.json
tsc
# Emit JS for just the index.ts with the compiler defaults
tsc index.ts
# Emit JS for any .ts files in the folder src, with the default settings
tsc src/*.ts
# Emit files referenced in with the compiler settings from tsconfig.production.json
tsc --project tsconfig.production.json
# Emit d.ts files for a js file with showing compiler options which are booleans
tsc index.js --declaration --emitDeclarationOnly
# Emit a single .js file from two files via compiler options which take string arguments
tsc app.ts util.ts --target esnext --outfile index.js
```

#JavaScript
	#TypeScript