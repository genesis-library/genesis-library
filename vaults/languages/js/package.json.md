 - bin section
 örneğin  create-react-app'ten bir proje oluşturduğunda react-scripts package'ı ile gelir ve bu package executable file'a sahiptir. 
 ```
 react-scripts start
 ```
bunu yapabilmemiz için bin section'ı içerisinde react-script'in kaynağı verilmiştir.

with npm -g, node will install symlink which makes the script accessable from *$PATH*
if without -g, *node_modules/.bin/command-name*

```
ls node_modules/.bin
npm exec or npx
```

make sure all your scripts start with shebang
```
#!/usr/bin/env node
```

```
# bin option in package.json 

$ cat node_modules/react-scripts/package.json 
{ ... "bin": { "react-scripts": "./bin/react-scripts.js" }, ... }

$ ls node_modules/react-scripts/bin 
react-scripts.js
```

./node_modules/.bin/cypress open



- main section
if main is not set, default: index.js
when a user installs and do ``` require("foo") ``` it will return exported objects from main. 

devDependencies vs dependencies
```npm install axios -D or --save-dev```
wont be installed if you pass
```npm install --production```