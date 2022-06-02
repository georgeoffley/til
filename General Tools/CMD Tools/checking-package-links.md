# Checking Package Links

[Source](https://www.rapidtables.com/code/linux/ls.html)

You can use the `ls` tool to check for symbolic links.

For example running

```bash
ls -al apps/package/node_modules
```

Will give you a list of files in the `apps/package/node_modules`. But pay attention to the printout.

```bash
lrwxr-xr-x   1 goffley  staff    58 May 12 10:43 redux -> ../../../node_modules/.pnpm/redux@4.1.2/node_modules/redux
```

The `->` denotes a symbolic link from the package to the left of the symbol pointing to the package in the right.

This is useful in a workspace like repo, where you're using something like [pnpm](https://pnpm.io/) to manage your package but still store your packages in one place with sym links in other packages.