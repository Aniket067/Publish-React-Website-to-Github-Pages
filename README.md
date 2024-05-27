# Vite React App

This guide explains how to create a React application using Vite and publish it to GitHub Pages.

## Prerequisites

Before you begin, ensure you have the following installed on your machine:

- [Node.js](https://nodejs.org/) (version 14 or higher)
- [npm](https://www.npmjs.com/) (usually comes with Node.js)

## Creating a Vite React App

1. **Create the project:**

   ```bash
     npm create vite@latest my-vite-react-app --template react
     cd my-vite-react-app
   ```
2. #### Install Node modules:
    ```bash
    npm install
    ```
3. #### Run the development server:
   ```bash
   npm run dev
   ```
Open http://localhost:5173 to view it in your browser.
 
## Setting Up the Project
1. #### Install gh-pages:
   ```bash
   npm install gh-pages --save-dev
   ```
2. #### Update vite.config.js:

Configure the base property to match your GitHub repository name.:
   ```bash
      import { defineConfig } from 'vite';
      import react from '@vitejs/plugin-react';

      export default defineConfig({
      plugins: [react()],
      base: '/your-repo-name/',
      });

   ```
3. #### Update vite.config.js:

Add deployment scripts-deploy and predeploy to package.json:
   ```bash
  {
    "scripts": {
    "dev": "vite",
    "build": "vite build",
    "predeploy": "npm run build",
    "deploy": "gh-pages -d dist"
  }
}


   ```
## Deploying to GitHub Pages
1. #### Push to Github
 ```bash
  git init
  git add .
  git commit -m "Initial commit"
  git branch -M main
  git remote add origin https://github.com/your-username/your-repo-name.git
  git push -u origin main
  ```
2. #### Build the app
 ```bash
  npm run build
 ```
3. #### Deploy the app
 ```bash
  npm run deploy
 ```

This will deploy the website to github pages and you can access them from Actions in Github
Your application should now be available at https://your-username.github.io/your-repo-name/.


### Notes:

- Replace `your-username` and `your-repo-name` with your actual GitHub username and repository name.
- Make sure to update the `base` property in `vite.config.js` with the correct repository name to ensure proper routing of paths.

