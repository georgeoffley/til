# Resolutions Block in Package.json

[Yarn RFC](https://github.com/yarnpkg/rfcs/blob/master/implemented/0000-selective-versions-resolutions.md)
[Yarn Package Explainer](https://yarnpkg.com/configuration/manifest/#resolutions)


When importing packages into your project they also pull in their dependencies. That can become a problem when you have nested dependencies of the same package but in different versions. One way that you can take care of this in yarn is using `resolutions` blocks in your `package.json`.

### Example

```json
  "resolutions": {
    "@types/react": "17.0.2",
    "@types/react-dom": "17.0.2"
  }
```

When packages pull in different version of the same dependencies you can specify which version the entire project should be using with the above code. When yarn tries to resolve dependencies and it is listed in the `resolutions` block yarn with use that dependency. 

This is useful as all the packages will use the version specified in the above block. There are some edge cases to this and could also cause compatibility issues with packages so it is important to take that into consideration.

#JavaScript
	#Yarn