# Running Yarn Commands In Workspaces

[Source](https://classic.yarnpkg.com/en/docs/cli/workspace)

When running `yarn` commands you can actually run these in specific workspaces.

For exmple if you want to add react and react-dom to one specific workspace you can run

```bash
yarn workspace awesome-package add react react-dom --dev
```

This will install those two packages in your `packages/awesome-package.json`.

#JavaScript
	#Yarn