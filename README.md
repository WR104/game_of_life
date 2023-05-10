# Deploying Rust WebAssembly on Github Pages: A Step-by-Step Guide

Rust is a programming language that's been gaining popularity in recent years, thanks in part to its powerful performance and memory safety features. Rust can also be compiled to WebAssembly (WASM), which allows it to run in the browser and interact with JavaScript code.

In this tutorial, we'll walk through the steps to deploy Rust WebAssembly on Github Pages. Github Pages is a free web hosting service offered by Github, which allows you to host static websites directly from your Github repository. By the end of this tutorial, you'll have a Rust WASM project up and running on Github Pages.

## Prerequisites

Before we get started, make sure you have the following tools installed:

- Rust (https://www.rust-lang.org/tools/install)
- Node.js (https://nodejs.org/en/download/)
- wasm-pack (https://rustwasm.github.io/wasm-pack/installer/)

You'll also need a Github account, and a Github repository set up for your Rust WASM project.

## Step 1: Download Template

You could download rust wasm template at here:
https://github.com/WR104/rust-wasm-template

## Step 2: git init

In the root directory of your project, run the following command:

``` shell
git init
```

## Step 3: Update Cargo.toml

You'll need to make some changes to your project's Cargo.toml file that are appropriate for you.

## Step 4: Update package.json

Next, you'll need to update the package.json file in your './www' directory. Change

``` json
 "dependencies": {
    "wasm-template-rust": "file:../pkg"
  },
```
into

``` json
  "dependencies": {
    "your-project-name": "file:../pkg"
  },
```

Replace your-project-name with the name of your Rust project. This tells Node.js to load the compiled WebAssembly module from the pkg (which we will create later) directory.

## Step 5: Modify HTML, CSS, and JavaScript

Import your project.

## Step 6: Build the Rust WASM project

In the root directory of your project, run the following command:

``` shell
wasm-pack build
```

This will compile your Rust code into a WebAssembly module, and place it in the pkg directory.

## Step 7: Install Node.js dependencies

Next, you'll need to build the Node.js project in your www directory. Navigate to the www directory, and run the following command:

``` shell
npm install
```

This will install any dependencies required by the Node.js project.

## Step 8: Build compiled  files

Then run the following command (also inside www directory):

``` shell
npm run build
```

This will build the Node.js project and generate a _dist_ directory containing the compiled JavaScript and CSS files.

## Step 9: Start the Node.js server

To test your project locally, you can start a Node.js server that will serve your compiled files. In the www directory, run the following command:

``` shell
npm run start
```

This will start a local server at http://localhost:8080, which you can access in your web browser.

## Step 10: Upload to the main branch

Now that your project is working locally, it's time to deploy it to Github Pages. 

Push everything in the root directory of your project to the main branch.
It helps to demonstrate your source codes

## Step 11: Create a gh-pages branch

then, create a new branch called gh-pages in your repository, which would be the live demo of your project.


## Step 12: Upload from the 'dist' directory

In the www directory, run the following command:

``` shell
npm run build
```

This will generate a new dist directory containing the compiled JavaScript and CSS files.

Then copy the contents of the 'dist' directory to the gh-pages branch.

## Step 13: Take a small sip of coffee

Your Rust WASM project should now be deployed to Github Pages! 

## Updating your deployed website

If you make changes to your Rust or JavaScript code, simply run

in root directory:
``` shell
wasm-pack build
```

in ./www directory:
``` shell
npm run build
npm run start
```

to rebuild and redeploy your project. Remember to commit and push your changes to the gh-pages branch in order to update your website.

## Conclusion

In this tutorial, we've covered the steps required to deploy a Rust WebAssembly project on Github Pages. By following these steps, you should now have a working Rust WASM project hosted on Github Pages, which can be accessed by anyone with an internet connection. With the power of Rust and WebAssembly, you can create high-performance web applications that run directly in the browser. Happy coding!
