# Reading Data from Files Using NodeJS

Resource: https://nodejs.org/api/fs.html#fspromisesreadfilepath-options

Node gives us built in file read operatoon using the NodeJS fs library. The version I learned on was the Promises library. They also have a synchronous version.

Args: 
- `path`: the location and file that you are reading from
- `options`: options for the file read operation. If you only pass in a string, as I did, the `readFile()` function treats the string as the encoding option.

Example:

```javascript
import { readFile } from "node:fs/promises";


export async function openFile(dir: string): Promise<string> {
    try {
        const fileRes = await readFile(dir, 'utf-8') // readFile() function
        return fileRes;
    } catch (error) {
        console.log(`Could not load file: ${error}`)
    }
}
```