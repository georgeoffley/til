# Fixing Errors In Project In VSCode

### Project
Engine

### Date
05/03/2022

### Technology
- VSCode

### The Problem

When I started I first set up my development environment by cloning the project and building it. Everything seemed to work as the project built without errors but I would see multiple issues with VSCode saying that imports could not be resolved; which cascaded down to other errors. It seems like VSCode did not know how to read the project.

### The Process

- I began by looking through the import errors. Each one was similiar saying that VSCode could not resolve the packages which were being imported into basically every typescript file. 
    - So I started Googling answers and they all has similiar solutions which were to run a `yarn install` or `npm install` to install the main packages. However, this made little sense as the setup file did all this with the help of [asdf](https://github.com/asdf-vm/asdf), which helps manage all the needed packages on a per project basis, and [direnv](https://direnv.net/docs/installation.html), which sets up needed environment variables as well as other stuff.
- After that I went through and tried to understand where all the various packages are kept.
    - This project uses a monorepo architecture with [scoped packages](https://blog.frankdejonge.nl/setting-up-a-typescript-mono-repo-for-scoped-packages/) so everything is in this repo and VSCode should be able to find it.
- I then tried running `yarn` to make sure all the packages are installed, and it ran without issues.
- After a bit of searching, I discovered the project had a `.vscode` directory with files for things like settings and suggested extensions for VSCode. I did not know what this was, so I did some digging and found these were [workspace settings](https://code.visualstudio.com/docs/editor/workspaces) that you can commit to your GitHub repo so that settings can be consistent for your project when people clone them. This was my answer.
    - I got that but did not know how to apply these settings to this project locally. So I did some Googling and could not find an answer. So I tried looking in the settings for a way to import those settings. Did not find anything
    - Just so happens I found the answer by doing my usuall workflow of opening the project directory directory in VSCode rather than just opening my `Dev` directory and going to the project directory. So that I can have the project directory in the right click menu for the icon and open it directly.
    - If you open a project with a `.vscode` directory at the root, VSCode will apply those workspace settings and prompt you to install any suggested extensions.

### Solution

[Workspace settings](https://code.visualstudio.com/docs/editor/workspaces) where the answer here. 

If you open a project with a `.vscode` directory at the root, VSCode will apply those workspace settings and prompt you to install any suggested extensions.

I did that and all the underlined errors went away.


#ProblemSolving