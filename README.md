# solutions-of-errors
A repo of solutions related to huge junks of errors


## Contents

- [You can use numbers for reference-style link definitions](#error-one)
- [Error: Invalid Configuration Object. Webpack has been initialised....](#error-two)



## Error one
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

## Error two
![error:2](https://cdn.discordapp.com/attachments/838608259413835806/841670767628124200/unknown.png)

### Reason
``` 
yet another error produced because of typo
```

### Solution
``try to start again with the following lecture and follow the instructor carefully.``

## Error three

![error:3](https://user-images.githubusercontent.com/54703305/129493969-94f41c90-6a58-452c-9dfe-7e325c0ca426.png)

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

## Error four
