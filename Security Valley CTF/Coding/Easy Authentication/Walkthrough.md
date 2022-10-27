# Easy Authentication

## Description
Let's start simple in this game. We have collected a piece of javascript. There is a validate function but we don't know the password... can you hack it?

Link: https://github.com/SecurityValley/PublicCTFChallenges/blob/master/coding/easy_authentication
## Solution

### Challenge Code
```JavaScript
const readline = require('readline').createInterface({
    input: process.stdin,
    output: process.stdout
});

readline.question('Please enter password \n', password => {
    console.log(`Gonna check if ${password} is correct`);
    readline.close();
    validate(password)
});

function validate(password) {
    const pass = [106,117,115,116,95,119,97,114,109,105,110,103,95,117,112];
    const pa = Array.from(password);

    for(let i = 0; i < pa.length; i++) {
        if(pa[i].charCodeAt(0) !== pass[i]) {
            throw new Error("pass violation. wrong credentials");
        }
    }

    banner(password);
}

function banner(payload) {
    console.info("that was great !!!");
    console.info("run the following command to get the flag.")
    console.info(`curl -X POST http://ctf.securityvalley.org:7777/api/v1/validate -H 'Content-Type: application/json' -d '{"pass": "${payload}"}'`)
}
```

### Reverse Challenge Code
```JavaScript
const pass = [106,117,115,116,95,119,97,114,109,105,110,103,95,117,112];
const pa = [];

for (let i = 0; i < pass.length; i++) {
  pa.push(String.fromCharCode(pass[i]));
}

console.log(pa.join(''));
```
`just_warming_up`

### Retrieve Flag
```
$ curl -X POST http://ctf.securityvalley.org:7777/api/v1/validate -H 'Content-Type: application/json' -d '{"pass": "just_warming_up"}'
{"Value": "SecVal{J4v45Cr1P7_15_57r4444N93}"}
```
`Flag: SecVal{J4v45Cr1P7_15_57r4444N93}`
