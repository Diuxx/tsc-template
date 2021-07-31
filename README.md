
# TSC TEMPLATE
This repository is used as template for typescript projects.

# START

```sh
git clone git@github.com:Diuxx/tsc-template.git
```

# CREATE THE SAME WITHOUT PULLING THIS REPO

1. init projet 
```sh
git init
npm init
```
2. download dependencies
```sh
npm i -D typescript ts-node @types/node @types/express
```
3. create files architecture
```sh
md src
echo >> src/index.ts
```
4. create tsconfig
```sh
tsc --init
```
5. update tsconfig

```json
{
  // This is an alias to @tsconfig/node12: https://github.com/tsconfig/bases
  "extends": "ts-node/node12/tsconfig.json",

  // Most ts-node options can be specified here using their programmatic names.
  "ts-node": {
    // It is faster to skip typechecking.
    // Remove if you want ts-node to do typechecking.
    "transpileOnly": true,

    "files": true,

    "compilerOptions": {
      // compilerOptions specified here will override those declared below,
      // but *only* in ts-node.  Useful if you want ts-node and tsc to use
      // different options with a single tsconfig.json.
    }
  }
}
```
6. Update package
```
{
  "main": "index.ts",
  "scripts": {
    "start": "ts-node src/index.ts",
    "build": "tsc",
    "test": "echo \"Error: no test specified\" && exit 1"
  }
}
```