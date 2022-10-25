# Fixing Build Errors From JSX Types and React Datetime Library

### Project
Combine

### Date
04/14/2022

### Technology
- JavaScript
- React
- [React Datetime](https://github.com/arqex/react-datetime)

### The Problem

When going to build the project with the react-datetime lib we were seeing errors with the project failing to build when at the `dist` stage.

The error was talking about the Datetime component not being a valid JSX object. The exact error was below.

```bash
=> ERROR [combine_dist build 4/4] RUN NODE_ENV=production yarn build                                     2.2s
------
 > [combine_dist build 4/4] RUN NODE_ENV=production yarn build:
#0 0.238 yarn run v1.22.15
#0 0.268 $ tsc && vite build
#0 2.180 src/components/ObservationTable/edit/DateTimeInputWidget.tsx(14,6): error TS2786: 'Datetime' cannot be used as a JSX component.
#0 2.180   Its instance type 'ReactDatetimeClass' is not a valid JSX element.
#0 2.180     The types returned by 'render()' are incompatible between these types.
#0 2.180       Type 'React.ReactNode' is not assignable to type 'import("/app/node_modules/@types/react-modal/node_modules/@types/react/index").ReactNode'.
#0 2.180         Type '{}' is not assignable to type 'ReactNode'.
#0 2.208 info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.
#0 2.208 error Command failed with exit code 2.
------
failed to solve: executor failed running [/bin/sh -c NODE_ENV=production yarn build]: exit code: 2
```

### The Process

- We first noticed the error when trying to build the project on another machine.
    - Nate noticed that the error was happening at a certain build step in the build process.
    - He commented out the docker compose node that was having the issue and we continued on with what we were doing.
    - After we finished what we needed I started looking into why that error came up.
- As the message made no sense to me, I began looking online for a solution
    - No results
- I then looked into the source code for the library to see if I can see what `render mismatch` was happening.
    - I was able to see all the attributes for the JSX object and get some more insight into it, but nothing to solve the problem I was seeing.
- I reached out to the group for help.
    - Nate had me switch the moment library's `@types` file in to the `devdependancies` section of our `package.json` file.
    - This had no effect.
- Nate then sent me [this stack overflow answer](https://stackoverflow.com/questions/71791347/npm-package-cannot-be-used-as-a-jsx-component-type-errors/71828113#71828113)
    - Implementing this solved the issue.

### The Solution

The solution was to add the following to our `package.json` file.

```json
"resolutions": {
  "@types/react": "17.0.2",
  "@types/react-dom": "17.0.2"
},
```

According to the answer given, this block will specify strict restrictions for dependencies of dependencies. The react it's needed is because `@types/react-dom` with a dependency of `@types/react`. Some packages might need to also import these dependencies and these are called "nested packages". 

If you import two different libraries which have the same dependency but a different version number than it is possible for those versions to be overwritten, which would cause problems. If a nested dependency is being resolved by yarn and that dependency is in the `resolutions` block yarn will look at that version number. [See here for a better explanation](https://github.com/yarnpkg/rfcs/blob/master/implemented/0000-selective-versions-resolutions.md). [You can also check this out as well which links to the previous resource](https://classic.yarnpkg.com/lang/en/docs/selective-version-resolutions/).

#ProblemSolving