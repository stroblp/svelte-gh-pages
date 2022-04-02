# Deploying a Svelte App to GitHub Pages

# Introduction

Short turorial to deploy Svelte app to GitHub Pages.

# svelte app

Create Svelte app

  ```
  npm create vite@latest
  ```

### Install the `gh-pages` npm package

Install the [`gh-pages`](https://github.com/tschaub/gh-pages) npm package 
 
    ```
    $ npm install gh-pages --save-dev
    ```


### Add a `homepage` property to the `package.json` file

Add a `homepage` property in this format\*: `https://{username}.github.io/{repo-name}`

    ```
    {
      "name": "svelte-app",
      "version": "0.1.0",
      "homepage": "https://{username}.github.io/{repo-name}",
      "private": true,
    ```

### Update the index.html file to include base path {repo-name}

    ```
        <link rel='icon' type='image/png' href='{repo-name}/favicon.png'>
        <link rel='stylesheet' href='/{repo-name}/global.css'>
        <link rel='stylesheet' href='/{repo-name}/build/bundle.css'>

        <script defer src='/{repo-name}/build/bundle.js'></script>
    ```

### Add deploy to the `package.json` file

Add a `deploy` to the `scripts` object:

    ```
    "build": "rollup -c",
    "dev": "rollup -c -w",
    "start": "sirv public --no-clear",
    "deploy": "gh-pages -d public"
    ```

### Deploy the Svelte app to GitHub Pages

Build and deploy the Svlete app to GitHub Pages

    ```
    $ npm run build
    $ npm run deploy
    ```

### The end

[`deployed svelte app`](https://stroblp.github.io/svelte-gh-pages/)
