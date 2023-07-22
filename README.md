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




### Testing Package <a name="test-package"></a>


### Publishing Package <a name="publish-package"></a>