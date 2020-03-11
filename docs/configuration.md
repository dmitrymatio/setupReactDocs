---
layout: default
title: Configuration
nav_order: 3
---

# Configuration
{: .no_toc }

The following are steps to configure the React environment.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---
## Step 1 - Set Compiler, Server and Loaders

Open **webpack-config.js** file and add the following code.
We configure the entry point for webpack to be main.js.
Output path is where our app will be served.
And we set our development server to listen on port 8001.

```js
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
   entry: './main.js',
   output: {
      path: path.join(__dirname, '/bundle'),
      filename: 'index_bundle.js'
   },
   devServer: {
      inline: true,
      port: 8001
   },
   module: {
      rules: [
         {
            test: /\.jsx?$/,
            exclude: /node_modules/,
            loader: 'babel-loader'
         }
      ]
   },
   plugins:[
      new HtmlWebpackPlugin({
         template: './index.html'
      })
   ]
}
```

Open the **package.json** and delete **"test" "echo \"Error: no test specified\" && exit 1"** inside **"scripts"** object. We are deleting this line since we will not do any testing in this tutorial. Let's add the **start** and **build** commands instead.

```
"start": "webpack-dev-server --mode development --open --hot",
"build": "webpack --mode production"
```
## Step 2 - index.html

This is just regular HTML. We are setting **div id = "app"** as a root element for our app and adding **index_bundle.js** script, which is our bundled app file.

```html
<!DOCTYPE html>
<html lang = "en">
   <head>
      <meta charset = "UTF-8">
      <title>React App</title>
   </head>
   <body>
      <div id = "app"></div>
      <script src = 'index_bundle.js'></script>
   </body>
</html>
```

## Step 3 - app.js and main.js

This is the first React component. We will explain React components in depth in a subsequent chapter. This component will render **Hello World**.

app.js
```js
import React, { Component } from 'react';
class App extends Component{
   render(){
      return(
         <div>
            <h1>Hello World</h1>
         </div>
      );
   }
}
export default App;
```

We need to import this component and render it to our root **App** element, so we can see it in the browser.

main.js
```js
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.js';

ReactDOM.render(<App />, document.getElementById('app'));
```
<br>
<div style="margin-left: 50px; display: flex; align-items: center;">
    <img src="https://raw.githubusercontent.com/dmitrymatio/setupReactDocs/gh-pages/docs/img/iconfinder_v-31_3162614.png"
      alt="note"
      style=" margin-right: 30px; width: 52px;" />
      <article style="border: 2px solid black; box-sizing: border-box; padding: 5px;"> <strong>Note:  </strong>Whenever you want to use something, you need to **import** it first. If you want to make the component usable in other parts of the app, you need to **export** it after creation and import it in the file where you want to use it.</article>
</div>
<br>

In your "VsCode", open the **.babelrc** file
Create a file with name **.babelrc** and copy the following content to it.

```
{
   "presets":["env", "react"]
}
```