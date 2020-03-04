---
layout: default
title: Installation
nav_order: 2
---

# Installation
{: .no_toc }

A step by step instruction on how to install the required software for setting up the react environment from scratch. By the end of this step you will have a empty react ready directory to work with. {: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

<div style="margin-left: 50px; display: flex; align-items: center;">
    <img src="raw.githubusercontent.com/dmitrymatio/setupReactDocs/gh-pages/docs/img/iconfinder_v-31_3162614.png"
      alt="note"
      style=" margin-right: 30px; width: 52px;" />
      <article style="border: 2px solid black; box-sizing: border-box; padding: 5px;"><strong>Note: </strong>The following step requires you to have basic knowledge about HTML CSS and Javascript. Moreover, a basic understanding of ES6 features, such as let, const, arrow function.</article>
</div>

## Step 1 - create a root folder

Open your "Terminal" and enter the following code.

```bash
$ cd Desktop
$ mkdir createReactApp
$ cd creatReactApp
$ code .
```

## Step 2 - create package.json file
To create any module or use any third-party library, it is required to generate a package.json file. This file contains a version of the module that you installed before. Moreover, if you want to share your folder with the other developer, they will know what package you used for this project.  

```bash
$ npm init -y
$ touch .gitingore
```

## Step 3 - install React and react dom
The (react) package provides the necessary method to define React components.
The (react-dom) package provides DOM-specific(client side) methods that can be used at the top level of your app and as an escape hatch to get outside of the React model if you need to. 

```bash
$ npm i react --save
$ npm i react-dom --save
```
Or you can just use one command

```bash 
$ npm i react react-dom --save
```

## Step 4 - install webpack

## Step 5 - install babel


