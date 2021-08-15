# solutions-of-errors
A repo of solutions related to huge junks of errors
all thanks to community members.

# Note 
``` 
don't lose patience follow the course till the end of the slide and if you not able to counter the error or bizzaro'ends showing no errors then come to this repo
```


## Contents

- [You can use numbers for reference-style link definitions](#error-1)
- [Error: Invalid Configuration Object. Webpack has been initialised....](#error-2)
- [Error: 3](#error-3)
- [Error: 4](#error-4)
- [Error: [webpack-cli] Error: Unknown Option -p](#error-5)
- [Error: 6](#error-6)
- [Error: 7](#error-7)
- [Error: 8](#error-8)
- [Error: 9](#error-9)
- [Error: 10](#error-10)
- [Error: 11](#error-11)


## Error 1
```
$ npm start
> floema@1.0.0 start
> npm run development
> floema@1.0.0 development
> webpack serve --progress --config webpack.config.development.js
[webpack-cli] Failed to load 'D:\Documents\dev\awwwards\floema\webpack.config.development.js' config
[webpack-cli] Error: Cannot find module './webpack-config'
Require stack:
- D:\Documents\dev\awwwards\floema\webpack.config.development.js
- D:\Documents\dev\awwwards\floema\node_modules\webpack-cli\lib\webpack-cli.js
- D:\Documents\dev\awwwards\floema\node_modules\webpack-cli\lib\bootstrap.js
- D:\Documents\dev\awwwards\floema\node_modules\webpack-cli\bin\cli.js
- D:\Documents\dev\awwwards\floema\node_modules\webpack\bin\webpack.js
    at Function.Module._resolveFilename (internal/modules/cjs/loader.js:880:15)
    at Function.Module._load (internal/modules/cjs/loader.js:725:27)
    at Module.require (internal/modules/cjs/loader.js:952:19)
    at require (D:\Documents\dev\awwwards\floema\node_modules\v8-compile-cache\v8-compile-cache.js:159:20)
    at Object.<anonymous> (D:\Documents\dev\awwwards\floema\webpack.config.development.js:4:16)
    at Module._compile (D:\Documents\dev\awwwards\floema\node_modules\v8-compile-cache\v8-compile-cache.js:192:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:1092:10)
    at Module.load (internal/modules/cjs/loader.js:928:32)
    at Function.Module._load (internal/modules/cjs/loader.js:769:14)
    at Module.require (internal/modules/cjs/loader.js:952:19) {
  code: 'MODULE_NOT_FOUND',
  requireStack: [
    'D:\\Documents\\dev\\awwwards\\floema\\webpack.config.development.js',
    'D:\\Documents\\dev\\awwwards\\floema\\node_modules\\webpack-cli\\lib\\webpack-cli.js',
    'D:\\Documents\\dev\\awwwards\\floema\\node_modules\\webpack-cli\\lib\\bootstrap.js',
    'D:\\Documets\\dev\\awwwards\\floema\\node_modules\\webpack-cli\\bin\\cli.js',
    'D:\\Documents\\dev\\awwwards\\floema\\node_modules\\webpack\\bin\\webpack.js'
  ]
}
 ``` 
 encountered by ``@walterlicinio#3771``

### Reason
```
could presist because of typo.
```

 ### Solution
``try to start again with the following lecture and follow the instructor carefully.``

## Error 2
![error:2](https://cdn.discordapp.com/attachments/838608259413835806/841670767628124200/unknown.png)
encounterd by ``@patmw#9134``

### Reason
``` 
yet another error produced because of typo
```

### Solution
``try to start again with the following lecture and follow the instructor carefully.``

## Error 3

![error:3](https://user-images.githubusercontent.com/54703305/129493969-94f41c90-6a58-452c-9dfe-7e325c0ca426.png)
encountered by ``@Mitch D. Lincoln#8833 & @Alexelso#6992``

### Reason
```
The error is triggered by the missing of
``module.exports``
in webpack.config.js
```
### Solution
```
continue with the course later down the course after adding 
``const dirNode = 'node_modules' & module.exports`` 
to 
``webpack.config.js``
will fix the error ^
```

## Error 4
```
error saying '@babel/core is missing'
```

### Reason
```
Because it isn't installed in devDependencies
```

### Solution
``npm install @babel/core``
if not work try to install it globally by going to root directory

how to go to root directory:
```
in mac

user$-imac % cd ~
```
and run command like
``npm install @babel/core -g``

## Error 5

![image](https://user-images.githubusercontent.com/54703305/129494810-d8c17b75-8880-4e2e-aa4d-14e56c3747ec.png)

### Reason 
```
the -p flag is deprecated in the latest build of webpack v5
```

### Solution

use this in package.json

```json
  "scripts": {
    "start": "npm run development",
    "development": "webpack serve --progress --config webpack.config.development.js",
    "build": "webpack --progress --config webpack.config.build.js"
  },
  ```
  
  ## Error 6
![image](https://user-images.githubusercontent.com/54703305/129494894-3380f4a8-6603-4f78-9096-c8aa9553a1ae.png)

### Reason
```
the problem is that you need to put the plugins outside the output object
```

### Solution
do this in webpack.config.build.js

```
const path = require("path");

const { merge } = require("webpack-merge");
const config = require("./webpack.config");

module.exports = merge(config, {
    mode: "production",

    plugins: [new CleanWebpackPlugin()],

    output: {
        path: path.join(__dirname, "public"),
    },
});
```

## Error 7
![image](https://user-images.githubusercontent.com/54703305/129495010-c3a5c4c2-f787-4f73-b056-486a6ac3a941.png)

### Reason
``
When you import something is like you are declaring a variable, that means you cannot import something, name it as a an then create a variable a.
``

### Solution 
name the import a diferent way

From:
```
import image from './image.png';

const image = 'Hello there, im a text';
```
To

```
import image from './image.png';

const text = 'Hello there, im a text';
```

## Error 8

![image](https://user-images.githubusercontent.com/54703305/129495056-ef17a530-7dc1-453b-8bfd-b6c86ba6eb1a.png)

### Reason & Solution
``
In order to work as expected, webpack need you to provide some conent inside the image folder! In this case, just put any image you want in the folder!
``

## Error 9
![image](https://user-images.githubusercontent.com/54703305/129495162-1971e68d-dc33-4705-9c11-55aae80727bf.png)

## Reason
``
Typo Issue 
``

## Solution
``
You can follow the course again and try to fix the typo in prismic or app.js file :(
``

## Error 10

Getting this error when i try to run ``npm run development``

```sh
floema@1.0.0 start
npm run development


floema@1.0.0 development
webpack serve --progress --config webpack.config.development.js

D:\Awwwards-courses\Floema\app D:\Awwwards-courses\Floema\assets D:\Awwwards-courses\Floema\styles
[webpack-cli] Invalid configuration object. Webpack has been initialized using a configuration object that does not match the API schema.
 - configuration.output should be an object:
this is my webpack.config.development.js file:
```
![image](https://user-images.githubusercontent.com/54703305/129495214-5ab61f2b-8d2f-4f51-b3fe-c1da54012768.png)

### Reason

`` can be a typo issue. if not please do ask for it in our discord channel ``

## Error 11

``I'm getting the following errors when I run npm start:``

![image](https://user-images.githubusercontent.com/54703305/129495263-19dbbe28-9f13-4518-8b1c-af52ce91291a.png)

### Reason
`` The Error Is because of the port using might be already in use. ``

### Solution 

``sudo kill PIDnumbergoeshere``
or
``pkill -f node``


