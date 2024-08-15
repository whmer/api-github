# API Github
- *https://api.github.com/users/*${username}

<center>
<img align=center src="./.git/git.jpg" width="80%"/>
</center>
<br>
<br>


## index.js
hello! here is the source code of script.js
```ts
//npm install axios readline
const axios = require('axios');
const readline = require('readline');

// Create an interface for user input
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

// Ask for the GitHub username
rl.question('Enter the GitHub username: ', async (username) => {
    try {
        // Fetch user information
        const userResponse = await axios.get(`https://api.github.com/users/${username}`);
        console.log('User Info:', JSON.stringify(userResponse.data, null, 2));

        // Fetch user's repositories
        const reposResponse = await axios.get(`https://api.github.com/users/${username}/repos`);
        console.log('Repositories:', JSON.stringify(reposResponse.data, null, 2));
    } catch (error) {
        console.error('Error fetching data from GitHub:', error.message);
    } finally {
        // Close the readline interface
        rl.close();
    }
});

```
<center>

```ts
               _         _ _   _           _     
    __ _ _ __ (_)   __ _(_) |_| |__  _   _| |__  
   / _` | '_ \| |  / _` | | __| '_ \| | | | '_ \ 
  | (_| | |_) | | | (_| | | |_| | | | |_| | |_) |
   \__,_| .__/|_|  \__, |_|\__|_| |_|\__,_|_.__/ 
        |_|        |___/                         
 
```
</center>