---
layout: default
title: Troubleshooting
nav_order: 8
---

# Troubleshooting
{: .no_toc }

This section will help you with troubleshooting errors in the environment.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Error: Cannot find module 'babel-preset-env'

```
Error: Cannot find module 'babel-preset-env' from '/Users/homerli/Desktop/Simple-react-app'<br>- Did you mean "@babel/env"?
```
How to solve: This happens because babel has updated their default setting in their package. Therefore, you need to change the **.babelrc** file to the following code and restart the server.
 
```json
{
	"presets": ["@babel/env", "@babel/preset-react"]
}
```

## Cannot find module "module" from path

How to solve: npm install the missing module.
