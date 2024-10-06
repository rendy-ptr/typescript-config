
# Typescript Config
You can use this for your project to make easily (for express js)

## Step
- follow in sequence

## How to use
1. initialization
``` bash
npm init
```
   OR
``` bash
npm init -y
```
2. Install typescript and ts-node for compiler
``` bash
npm install -D typescript ts-node
```
3. Initialization tsconfig or copy from my [tsconfig.json](https://github.com/rendy-ptr/typescript-config/blob/main/express/tsconfig.json)
         (prefer copy from my config)
``` bash
npx tsc --init
```
4. Copy my custom scripts from file [package.json](https://github.com/rendy-ptr/typescript-config/blob/main/express/package.json) or copy this
``` bash
{
    "scripts": {
        "start": "npx tsc -w",
        "dev": "npx nodemon",
        "build": "tsc",
        "format": "prettier --write ."
    }
}
```
5. Install Nodemon
``` bash
npm install --save-dev nodemon
```
OR
``` bash
npm install -D nodemon
```
6. Configuration nodemon, you can copy from my [nodemon.json](https://github.com/rendy-ptr/typescript-config/blob/main/express/nodemon.json) or copy this
``` bash
{
    "watch": ["src"],
    "ext": "ts",
    "exec": "npx ts-node ./src/index.ts"
}
```
6. Install Express
``` bash
npm install express
```
AND
``` bash
npm install -D @types/express
```
7. Install ESLint
``` bash
npm install eslint --init
```
Answer :
- y
- y
- choose option number 3
- choose javascript modules
- choose none of theese
- choose Yes
- choose node
- choose option popular style
- choose standard
- choose json
- choose Yes
- choose npm (if you use npm)

8. Install some dev dependencies
``` bash
npm install -D @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint eslint-config-standard eslint-plugin-import eslint-plugin-node eslint-plugin-promise eslint-plugin-standard
```
9. add parser after extends line in .eslintrc.json file or if you need simple method just copy from my [.eslintrc.json](https://github.com/rendy-ptr/typescript-config/blob/main/express/nodemon.json)
``` bash
"parser": "@typescript-eslint/parser",
```
10. Delete overrides

11. after parserOptions line add plugins
``` bash
"plugins": ["@typescript-eslint"],
```
12. after plugins line add ignorePatterns
``` bash
"ignorePatterns": ["**/build/*", "**/node_modules/*", "**/public/*"],
```
13. install prettier for code formatter
``` bash
npm install --save-dev --save-exact prettier
```
14. create file `.prettierrc` you can copy config from my [,prettierrc.json](https://github.com/rendy-ptr/typescript-config/blob/main/express/.prettierrc) file or copy this
``` bash
{
    "arrowParens": "always",
    "printWidth": 120,
    "semicolon": false,
    "singleQuote": true,
    "trailingComma": "none"
}
```
15. create file `.prettierignore` you can copy config from my [,prettierignore.json](https://github.com/rendy-ptr/typescript-config/blob/main/express/.prettierignore) file or copy this
``` bash
eslintrc.json
prettierrc.json
package.json
package-lock.json
tsconfig.json
CHANGELOG.md
readme.md
nodemon.json
yarn.lock
dist
build
public
node_modules
vercel.json
```




## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
This project is open source and available under the [MIT License](LICENSE).

  
