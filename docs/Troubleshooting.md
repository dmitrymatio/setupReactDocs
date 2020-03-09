---
layout: default
title: Troubleshooting
nav_order: 7
---

# Troubleshooting
{: .no_toc }

This section is to show you what to do when you having a error in the code.  {: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Error: Cannot find module 'babel-preset-env' from '/Users/homerli/Desktop/Simple-react-app'<br>- Did you mean "@babel/env"?

How to solve: This happens because babel has updated their default setting in their package. Therefore, you need to change the **.babelrc** file to this
 
```json
{
	"presets": ["@babel/env", "@babel/preset-react"]
}
```

## Cannot find module "module" from path

How to solve: npm install the missing module.
