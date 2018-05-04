Engineer practice of javascript.

Node 应用由模块组成，采用CommonJS 模块规范。 每个文件就是一个模块.Module must be load **synchronously**
Default syntax is already commonJs.

AMD and system js,Module can be load **asynchronously** . 

For some special reason that will js will  be concatenated in one file in typescript

A node project file export one file declared in package.json .

Babel=>Convert ES6 Syntax to ES5 Syntax.


Browserify/Webpack/Rollup turn common js/Amd modules to big one js file that works in client(Resolve the require)

http://www.ruanyifeng.com/blog/2015/05/commonjs-in-browser.html