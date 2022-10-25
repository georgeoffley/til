# Project References

[Source](https://www.typescriptlang.org/docs/handbook/project-references.html)

You can partition out TS project using project references.

In the top level `tsconfig` file, (`tsconfig` file at the root of the project) you can put references to each of your projects.

When modules import from a references project will load in the outputted `.d.ts` file reducing compile times.

From the docs:

> By separating into multiple projects, you can greatly improve the speed of typechecking and compiling, reduce memory usage when using an editor, and improve enforcement of the logical groupings of your program.

Example code in the `tsconfig.json` file.

```json
{
    "compilerOptions": {
        // The usual
    },
    "references": [
        { "path": "../src" }
    ]
}
```

#JavaScript
	#TypeScript