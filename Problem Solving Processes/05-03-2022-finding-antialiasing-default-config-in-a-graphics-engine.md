# Finding a setting in source

### Project
Work Project

### Date
05/03/2022

### Technology
- TypeScript
- VSCode

### The Problem

Ticket for updating the default value for antialiasing on export. I could not find the files needed for setting the default without help.

### The Process

- Asked my supervisor for help in finding where antialiasing might be. 
- First we ran a whole project search in VSCode looking for references to `Antialiasing` as it shows up in the export window so looking for just that word is a good start.
- We ended up in the same place I had been before, the `projects/packages/config/src/defaultProjectAsset.ts` where we updated the quality.
    - That might not have solved the issue, I am still investigating.
- We did also find where the asset is created and has everything set for it.
    - We had to use the project search, but also enable the `Match Case` and `Use Whole Word` options in the search panel.
    - It also helped for us to add `*.ts` to the `files to include` section so that we were only looking for TypeScript files.

### Solution

We managed to find it by doing the following

- Looking for a word we see in the UI, `Antialiasing`
- Searching for the word using the universal search
- Setting the `Match Case` and `Use Whole Word` options.
- And add `*.ts` to `files to include` so that we were only searching for TS files.

Those are all great tools for searching this codebase.

#ProblemSolving