# Writing to Files Using NodeJS

Resource: https://nodejs.org/api/fs.html#fspromiseswritefilefile-data-options

Node gives us built in file operatoon using the NodeJS fs library. The version I learned on was the Promises library. They also have a synchronous version.

Args: 
- `file`: the location and file that you are writting to
- `data`: the data being written

When writing JSON information I had to use `JSON.stringify(recordsVar, null, 2)`. I also had to make sure the JSON data looked formatted so I added the null and 2 arguments for `JSON.Strigify()`.

```javascript
import { writeFile } from 'node:fs/promises';

// Write records marked for migration
fileWriter(
    'path/file.json',
    JSON.stringify(recordsJSON, null, 2)
)
```

#JavaScript