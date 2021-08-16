# solutions-of-errors

made for the amazing course available on awwwards: https://www.awwwards.com/academy/course/building-an-immersive-creative-website-from-scratch-without-frameworks

A repo of solutions related to huge bunch of errors
all thanks to community members.

# Note 
``` 
don't lose patience follow the course till the end of the slide and if you not able to counter
the error or bizzaro'ends showing no errors then come to this repo
```


## Errors 

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
- [Error: 12](#error-12)
- [Error: 13](#error-13)
- [Error: 14](#error-14)
- [Error: 15](#error-15)
- [Error: 16](#error-16)

## Questions
- [Question 1](#question-1)
- [Question 2](#question-2)
- [Question 3](#question-3)
- [Question 4](#question-4)
- [Question 5](#question-6)
- [Question 7](#question-7)
- [Question 8](#question-8)
- [Question 9](#question-9)
- [Question 10](#question-10)


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

#### For Windows

![Screenshot 2564-08-16 at 7 14 39 PM](https://user-images.githubusercontent.com/54703305/129573481-25701015-030f-4511-9ab3-534873d3bd54.png)


### Students Faced this error in some other possibilities
#### if you have ``exclude`` statements in your rules for babel 
``The do this``
![Screenshot 2564-08-16 at 7 22 23 PM](https://user-images.githubusercontent.com/54703305/129574611-3e045368-a76c-4e04-8b04-91666e1a8e82.png)


## Error 12
![image](https://user-images.githubusercontent.com/54703305/129574830-e51482bf-1f89-4283-a8be-567efa8cb462.png)

### Reason 
`` This is happening because you haven't installed concurrently globally.``

### Solution

``npm install -g concurrently`` by going to your root dir ``~``

## Error 13

```
Error: D:\Awwwards-courses\Floema\views\pages\home.pug:6:1

Unexpected block content


home.pug:
extends ../base.pug

block variables 
  - var template = 'home' 

block content 
  h1.collections__title Home


base.pug:

  body
    include ./partials/preloader
    include ./partials/navigation

    .content#content(data-template=template)
      block body
```

### Solution

Change ``block body`` to ``block content`` in base.pug

## Error 14
![image](https://user-images.githubusercontent.com/54703305/129580836-3c795929-a13c-4f51-878c-9b1957131a19.png)

### Answer 

[stackoverflow](https://stackoverflow.com/questions/34600932/npm-eperm-operation-not-permitted-on-windows)

## Error 15

``Hi I am at the implementation of pug prismic and express part. Sometimes the routing works perfectly fine, sometimes it throws this error. Especially when I navigate between /collections and /home, it has to fetch collection the second time , it will fail for sure.   Is it possible that Prismic is unstable for unpaid users? Thanks in advance.``
![image](https://user-images.githubusercontent.com/54703305/129581549-23249155-7b50-42c6-abce-9cd0fc92f878.png)

### Reason 
``bodyparser is commented``

### Solution
`` Use it``

but why to comment body parser. because a student acknowledged it as a depricated if you guys wants to use any other solution
then you can use this 

```app.use(express.json())
app.use(express.urlencoded())
```

## Error 16

![image](https://user-images.githubusercontent.com/54703305/129582106-20b2b6b2-6f42-4b4e-a2ec-24c237c9960b.png)

### Reason 

``It's an mini typo``

### Solution

``if section.slice_type == 'highlight'``
if this not able to solve the problem do follow the lecture again carefully ^


# Questions


## Question 1
```js
why does the development config script need:

output: {
    path: path.resolve(__dirname, "public"),
  },
``` 
by @interactive-harp#6998

### Answer
``Here your telling webpack that the file it needs to send to the browser is this one!`` by @lunactec#1507

## Question 2
``why do we need to use express.js when we could use a webpack related plugin to use local server?`` by @interactive-harp#6998

### Answer
``For the ruting system and the integration of prismic
plus its really easy to transform this website into a funcitonal ecommerce just becuase of that
That means that, becuase of using express, every major change related to the product its easier to handle
This is a really good resource to learn node and express.js basics! -> https://youtu.be/Oe421EPjeBE`` by @lunactec#1507

## Question 3

``What if we don't need any back-end or e-commerce.... then no neeed for express`` by @interactive-harp#6998

### Answer

``If you implement the routing client-side then yes, i think so`` by @lunactec#1507
``If you don't want to have a CMS and BE integration, using routes is completely fine.`` by @bizarro#7465 ( course instructor )

## Question 4

``is there an advantage to use prismic than those?`` by @HenHeym#1915

### Answer 4

`` think possibly the Express integration. Usually it's just hard to do it in other CMS.`` by @bizarro#7645 ( course instructor )

`` Internationalization is one for sure
https://payloadcms.com/#express -> This one is in my scope! They have an integration with express too `` by @lunactec@1507

## Question 5

``if you ever need to implement a store in one of your sites, do you start from the same base you have, or do you use something else? For example on garoaskincare, how did you do it?`` by @HenHeym#1915

### Answer 5 

``y``

## Question 6

``does digital ocean and express need eachothers support? to put our site on digital ocean, do we need express/ a backend?
usually i use github pages thats why wondering`` by @interactive-harp#6998

### Answer 6 

``Digital ocean its a cloud provider that let us deploy our code in there. In it self, it has built in support for express, yes. You can also reffer the last 2 classes to get more information about the deployment process. It depends of the implementation, but you dont really need a backend to deploy in a cloud provider!`` by @lunactec#1507

## Question 7

``to use connect with a cms, a backend such as express is needed right?`` by @interactive-harp#6998

### Answer 7

``Not really, it depends on the cms your using
You can implement prismic without backend
https://prismic.io/docs/technologies/integrating-with-an-existing-project-javascript`` by @lunactec#1507

## Question 8 

``Whats the downfall of client over backend implementation?`` by @interactive-harp#6998

### Answer 8
``Well, i dont think there is an special reason implementing a backend instead of a full client aprouch in this specific project, rather than bizarro's personal preference and experience
Personally, i really like the backend aproach, it makes it simpler to maintain and i like backend routing too! Plus you can easely integrate alot of services! And its maybe more productive than a full client aproach.`` by @lunactec#1507

``don't let the back end implementation let you down. I know it's not 100% related, but someone will ask you to make an editable website in the future, and you'll know how to do it. :smile:
After you do the full course, if you check out this repo here: https://github.com/lhbizarro/bizar.ro/. You'll be able to understand how to do everything in GH Pages.`` by @bizarro#7645

## Question 9
``is  prismic allows a client to edit the site without them needing to know code?`` by @sweatythonk#7907

### Answer 9
``Yeah, if they have access to the primsic project, you can do that!`` by @lunactec#1507


## Question 10

``What about the connection issue? I doubt this is a Prismic issue, because for me it works half of the time. but It's frustrating to restart the server and wait for it to work.`` by @Weijie#0237

### Answer 10
``First put the express parsers, maybe that solve part of the issue!`` by @lunactec#1507

