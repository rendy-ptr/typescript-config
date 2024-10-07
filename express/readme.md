
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
    "build": "tsc && cp .env ./build/.env",
    "format": "prettier --write .",
    "prod": "node ./build/index.js"
  }
}
```
5. Install Nodemon
``` bash
npm install --save-dev nodemon
```
6. Configuration nodemon, you can copy from my [nodemon.json](https://github.com/rendy-ptr/typescript-config/blob/main/express/nodemon.json) or copy this
``` bash
{
    "watch": ["src/**/*.ts"],
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
9. add this in .eslintrc.json file or if you need simple method just copy from my [.eslintrc.json](https://github.com/rendy-ptr/typescript-config/blob/main/express/.eslintrc.json)
``` bash
{
  "env": {
    "es2021": true,
    "node": true
  },
  "extends": "standard-with-typescript",
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaVersion": "latest",
    "sourceType": "module",
    "project": ["**/tsconfig.json"]
  },
  "plugins": ["@typescript-eslint"],
  "ignorePatterns": ["**/build/*", "**/node_modules/*", "**/public/*", "**/tsconfig.json"],
  "rules": {
    "@typescript-eslint/restrict-template-expressions": "off"
  }
}
```
10. install prettier for code formatter
``` bash
npm install --save-dev --save-exact prettier
```
11. create file `.prettierrc` you can copy config from my [,prettierrc.json](https://github.com/rendy-ptr/typescript-config/blob/main/express/.prettierrc) file or copy this
``` bash
{
    "arrowParens": "always",
    "printWidth": 80,
    "semicolon": false,
    "singleQuote": true,
    "trailingComma": "none",
    "tabWidth": 2
}
```
12. create file `.prettierignore` you can copy config from my [,prettierignore.json](https://github.com/rendy-ptr/typescript-config/blob/main/express/.prettierignore) file or copy this
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
13. install library husky and pretty-quick for pre-commit
``` bash
npm i -D husky pretty-quick
```

14. edit file `package.json`
``` bash
{
  "scripts": {
    "start": "npx tsc -w",
    "dev": "npx nodemon",
    "build": "tsc && cp .env ./build/.env",
    "format": "prettier --write .",
    "prod": "node ./build/index.js",
    "prepare": "husky install",
    "check-format": "prettier --check .",
    "check-lint": "eslint . --ext ts --ext tsx --ext js",
    "check-types": "tsc --pretty --noEmit"
  },
  "husky": {
    "hooks": {
      "pre-commit": "npx pretty-quick --staged ng lint bg test",
      "pre-push": "ng build --aot true" 
    }
  }
}

```
15. run this to install husky
``` bash
npm run prepare
```
16. create a `pre-commit` file inside the `_husky` folder and fill it with this
``` bash
#!/bin/sh
. "$(dirname "$0")/_/husky.sh"

echo ' Styling, testing and building your project before commit...'

# Check Prettier
npm run check-format ||
(
    echo 'Prettier Check Failed. Run npm run format, add changes and try commit again.';
    false;
)

# Check ESLint
npm run check-lint ||
(
    echo 'ESLint Check Failed. Make the required changes listed above, add changes and try commit again.';
    false;
)

# Check tsconfig
npm run check-types ||
(
    echo 'Failed type check. Make the changes require above, add changes and try commit again.';
    false;
)

npm run build ||
(
    echo 'Your Build failed. view the errors above';
    false;
)

echo "Success Commit...";
```


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
This project is open source and available under the [MIT License](LICENSE).

  
