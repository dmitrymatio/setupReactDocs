---
layout: default
title: First React Page
nav_order: 5
---

# How to set up your first react page with JSX and CSS.
{: .no_toc }

This is a step by step instruction on how to build your first react page with JSX and css. Please follow the instruction thoroughly.

{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

<div style="margin-left: 50px; display: flex; align-items: center;">
    <img src="https://raw.githubusercontent.com/dmitrymatio/setupReactDocs/gh-pages/docs/img/iconfinder_v-31_3162614.png"
      alt="note"
      style=" margin-right: 30px; width: 52px;" />
      <article style="border: 2px solid black; box-sizing: border-box; padding: 5px;"> <strong>Note: </strong>Please follow the guide thoroughly, otherwise, it may not work as expected.</article>
</div>

## Step 1 - Install loader
 
In order to add style in your website, you must install css-loader first. Its purpose is to load the CSS file.
<br>
<div style="margin-left: 50px; display: flex; align-items: center;">
    <img src="https://raw.githubusercontent.com/dmitrymatio/setupReactDocs/gh-pages/docs/img/iconfinder_v-31_3162614.png"
      alt="note"
      style=" margin-right: 30px; width: 52px;" />
      <article style="border: 2px solid black; box-sizing: border-box; padding: 5px;"> <strong>Note: </strong>If you don't know how to access your "Terminal" in your Vscode. The shortcut is <i>Ctrl + i</i></article>
</div>
<br>
In your VScode "Terminal", and type

```bash
$ npm install css-loader --save-dev
$ npm install style-loader --save-dev
```

After installation, your **package.json** should look like this

```json
{
    "name": "createReactApp",
	  "version": "1.0.0",
	  "description": "",
	  "main": "index.js",
	  "scripts": {
  	  "start": "webpack-dev-server --mode development --open --hot",
		  "build": "webpack --mode production"
	  },
	  "keywords": [],
	  "author": "",
	  "license": "ISC",
	  "dependencies": {
    		"react": "^16.13.0",
	  	"react-dom": "^16.13.0",
	  	"webpack": "^4.42.0",
	  	"webpack-cli": "^3.3.11",
	  	"webpack-dev-server": "^3.10.3"
	  },
	  "devDependencies": {
    	"@babel/core": "^7.8.7",
	  	"@babel/preset-env": "^7.8.7",
	  	"@babel/preset-react": "^7.8.3",
	  	"babel-loader": "^8.0.1",
	  	"css-loader": "^3.4.2",
	  	"html-webpack-plugin": "^3.2.0",
      "style-loader": "^1.1.3"
	  }
} 
```


## Step 2 - Change your **webpack.config.js** file

To use the package you just installed, you need to change you **webpack.config.js** file.

In your **webpack.config.js** file, you need to add this in the rule section.

```json
{ test: /\.css$/, loader: ["style-loader", "css-loader"] }
```


## Step 3 - Install babel plugin

Because we are using the class base react in this instruction; therefore, in order to use class components, we need to install a babel plugin.

In your VScode "Terminal", and type

```bash
$ npm install @babel/plugin-proposal-class-properties --save-dev
```

After installation, your **package.json** should look like this

```json
{
    "name": "createReactApp",
	  "version": "1.0.0",
	  "description": "",
	  "main": "index.js",
	  "scripts": {
  	  "start": "webpack-dev-server --mode development --open --hot",
		  "build": "webpack --mode production"
	  },
	  "keywords": [],
	  "author": "",
	  "license": "ISC",
	  "dependencies": {
    	"react": "^16.13.0",
	  	"react-dom": "^16.13.0",
	  	"webpack": "^4.42.0",
	  	"webpack-cli": "^3.3.11",
	  	"webpack-dev-server": "^3.10.3"
	  },
	  "devDependencies": {
    	"@babel/core": "^7.8.7",
      "@babel/plugin-proposal-class-properties": "^7.8.3",
	  	"@babel/preset-env": "^7.8.7",
	  	"@babel/preset-react": "^7.8.3",
	  	"babel-loader": "^8.0.1",
	  	"css-loader": "^3.4.2",
	  	"html-webpack-plugin": "^3.2.0",
      "style-loader": "^1.1.3"
	  }
} 
```


## Step 4 - Configure the **.babelrc** file

In order to make usage of the babel plugin, we need to add a configuration to the **.babelrc** file. 

In your **.babelrc** file, you need to change your **.babelrc** file to this

```json
{
    "presets": ["@babel/env", "@babel/preset-react"],
    "plugins": [["@babel/plugin-proposal-class-properties", { "loose": true }]]
}
```


## Step 5 - Create folders and files

This step is not very important, but it will be best if you want to keep your folder looks clean.

Open your Vscode "Terminal" and start typing.

```bash
$ mkdir App
$ cd App
$ mkdir JS
$ mkdir stylesheet
$ cd JS
$ touch userInput.js
$ touch userOutput.js
$ cd ../stylesheet
$ touch app.css

##At last, you need to move your App.js in the App folder
```

After this step, you should see this in the left sidebar in your Vscode.

![screenshot eight](./img/8.png)


## Step 6 - Modify **App.js**

Add new JSX code to make your own pages. JSX allows you to write HTML code in JavaScript way, without using syntax like createElement() or appendChild().

Add code belows:

```js
import React, { Component } from "react";
import IN from "./JS/userInput";
import OUT from "./JS/userOutput";
import "./stylesheet/app.css";

class App extends Component {
    state = {
      condition: [
        {
          type: "REACT"
        },
        {
          type: "C++"
        }
      ]
    };

    SwitchName = event => {
      this.setState({
        condition: [
          {
            type: event.target.value
          },
          {
            type: "C++"
          }
        ]
      });
    };

    render() {
      return (
        <div className="App">
          <h1 className="project_title">This is my Your React Project</h1>
          <OUT type={this.state.condition[0].type}>
            This is the child of first box
          </OUT>
          <OUT type={this.state.condition[1].type} />
          <IN name={this.state.condition[0].type} changed={this.SwitchName} />
        </div>
      );
    }
} 
export default App;
```


## Step 7 - Add style code

In this step, you will know how to add more css code to your own react project.

Open you **app.css** file, and add more css code in it. At this stage, you can add more personal preference to the css code to make it more appealing.

Add code below:

```css
.project_title {
  color: darkred;
}

.p {
  margin: 10px auto;
  box-sizing: border-box;
  padding: 30px;
  border: 1px solid #000000;
  font-weight: bolder;
  width: 300px;
}

.p:nth-child(3) {
  cursor: pointer;
}

.p:nth-child(3):hover {
  color: rebeccapurple;
}

.inputspace {
  width: 300px;
}
```


## Step 8 - Add JavaScript to **userInput.js** file

At this step, you will need to add more JSX code in your **userInput.js** file. In your **userInput.js**, and add some JSX in it. 

Add code below:

```js
import React from "react";
const userInput = props => {
    return (
      <div>
        <input
          className="inputspace"
          type="text"
          onChange={props.changed}
          value={props.name}
        />
      </div>
    );
};

export default userInput;

```


## Step 9 - Add JavaScript to **userOutput.js** file

At this step, you will need to add more JSX code in your **userOutput.js** file. In your **userOutput.js**, and add some JSX in it. 

Add code below:

```js
import React from "react";

const userOutput = props => {
    return (
      <div className="p">
        <p onClick={props.click}>{props.type} is fine</p>
        <p>{props.children}</p>
      </div>
    );
  };

export default userOutput;
```


## Step 10 - npm start

At this step and also your last step, open your VScode "Terminal, " and start typing.

```bash
$ npm start
```

After the build is done, you will see this in "http://localhost:8001/"

![screenshot nine](./img/9.png)


# Congrats you have your first react page now