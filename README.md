# Creating An NPM Package


[NPM Docs](https://docs.npmjs.com/)


### Contents 

* [What Is NPM?](#npm)
* [Creating A Git Repository](#create-repo)
* [Creating Package](#create-package)
* [Testing Package](#test-package)
* [Publishing Package](#publish-package)


### What Is NPM? <a name="npm"></a>

- NPM is the world's largest software registry. Open source developers from every continent use NPM to share and borrow packages, and many organizations use NPM to manage private development as well.

##### NPM consists of three distinct components:

- The website
- The Command Line Interface (CLI)
- The registry

<br>

- Use the website to discover packages, set up profiles, and manage other aspects of your npm experience. For example, you can set up organizations to manage access to public or private packages.
https://www.npmjs.com/

<br>

- The CLI runs from a terminal, and is how most developers interact with npm.
https://docs.npmjs.com/cli/v9/commands/npm

<br>

- The registry is a large public database of JavaScript software and the meta-information surrounding it.
https://docs.npmjs.com/cli/v9/using-npm/registry

### Creating A Git Repository <a name="create-repo"></a>

- Here a very basic JavaScript app is developed and created as an NPM package.

- Follow the steps below to create your first NPM package. 

##### Steps 

- Create a git repository at local. Here, the example is a repo called 'first-npm-package'

- Add `git` to repo and publish it to GitHub, a hosting web platform for repositories.

- Add `.gitignore` file in order to test the package later on. 

- Add 2 folders (package and tests). package folder is used to write functions to create NPM package, whereas tests folder is used to test the package before publishing to NPM.

### Creating Package <a name="create-package"></a>

> **Next Step:** Create package.json file for the package.

- The `package.json` file is an essential component in projects that use Node.js or NPM (Node Package Manager). It is commonly found in Node.js projects and it serves several important purposes such as `dependency management`, `version control for dependencies`, `scripts`, `metadata`  and `project initialization`.

- package.json is essentially just a way to describe what your package does. So, it's really important to put as much information as possible. 

- Locate `package` folder at terminal.
`cd package`

- Write this command to create package.json file inside package folder.
`npm init`

* package name: check-for-name
* version: 1.0.0
* description: Is the name of user Berke and surname Sayin?
* entry point: index.js
* test command: empty
* git repository: https://github.com/berkeJr/first-npm-package
* keywords: Name 
* author: Berke Sayin
* license: empty

<br>

- Here is the `package.json` file created inside `package` folder:

```js
{
  "name": "check-for-name",
  "version": "1.0.0",
  "description": "Is the name of user Berke and surname Sayin?",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/berkeJr/first-npm-package.git"
  },
  "keywords": [
    "Name"
  ],
  "author": "Berke Sayin",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/berkeJr/first-npm-package/issues"
  },
  "homepage": "https://github.com/berkeJr/first-npm-package#readme"
}

```
##### Create index.js inside package

- Important point here is that main file is `index.js`. So inside `package` folder, we create a file called `index.js`, and inside here is where all of code for package is written.

`package/index.js` 

```js
const isNameBerke = (string) => {
  return string === "Berke";
};

const isSurnameSayin = (string) => {
  return string === "Sayin";
};

module.exports = {
  isNameBerke,
  isSurnameSayin,
};

```

### Testing Package <a name="test-package"></a>

- Testing locally is essential before publishing the package. To do that this command is used: `npm link`

- Make sure you locate `package` at terminal and type in the command `npm link`.

##### npm link 

- The `npm link` command is used for locally testing and developing npm packages. It allows you to create a symbolic link between a globally installed npm package and a local working directory. 

- This is particularly useful when you want to make changes to a package and see the immediate effects in a project that depends on it, without the need to publish the package to the npm registry after every change.

<br>

- Create a `script.js` file inside `tests` folder.

`tests/script.js`

```js
const { isNameBerke, isSurnameSayin } = require("check-for-name");


console.log(isNameBerke("Berke")); // true
console.log(isNameBerke("Hamza")); // false

console.log(isSurnameSayin("Sayin")); // true
console.log(isSurnameSayin("Yilmaz")); // false

```

- The name `Berke` and surname `Sayin` are returned as `true` and others are `false` according to the functions for `package` at `package/index.js` file.

##### npm link package-name

- The `package` is needed at tests folder but haven't been deployed yet. So, the solution here is to use `link`.

- Go to terminal and locate at `tests` folder. 

- Type in the command `npm link package-name` which is `npm link check-for-name`.

- Then, at terminal run the command: `node scripts.js`


<br>
### Publishing Package <a name="publish-package"></a>

- Code is written and tested successfuly, which means it is ready to be published.

##### Steps to publish the package

- Go to https://www.npmjs.com/signup and create an account if you don't have any. 

- Open terminal, locate `package` folder.

- Use `npm login` command to login with the account created earlier.

- Use `npm publish` command to publish the package to NPM. 

- Publishing is successfully: Publishing to https://registry.npmjs.org/ with tag latest and default access + check-for-name@1.0.0

- If you continue to develop the project after first release which is version `1.0.0`, you just make your changes, and then go to `package.json`, change the version to something like `1.0.1`, and then publish it. That's all!!

### Conclusion

- In this short tutorial, I tried to show how an NPM package can be created, tested and published easily. 