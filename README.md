# Deploying Svelte App to GitHub Pages

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
  "name": "svelte-app",
  "version": "0.1.0",
  "homepage": "https://{username}.github.io/{repo-name}",
  "private": true,
   ```

### Add base url in vite.conf.js
  ```
  export default defineConfig({
  plugins: [svelte()],
  base:"/{repo-name}/"
  })
  ```
### Add deploy to the `package.json` file

Add a `deploy` to the `scripts` object:

  ```
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "deploy": "gh-pages -d dist"
  }
  ```

### Deploy the Svelte app to GitHub Pages

Build and deploy the Svlete app to GitHub Pages

  ```
  $ npm run build
  $ npm run deploy
   ```

### The end

[`deployed svelte app`](https://stroblp.github.io/svelte-gh-pages/)
