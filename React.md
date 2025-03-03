# Create a React App
## Step for require
- Create a file folder, we call it react app name
  
    mkdir quantify-ass
- Into the file folder 'quantify-ass', and Initialization
  
    cd quantify-ass
    npm init -y
- Install react and core packages
  
    npm install react react-dom
- Install webpack kits
  
    npm install --save-dev webpack webpack-cli webpack-dev-server
- Install babel for JSX 和 ES6+
  
    npm install --save-dev @babel/core @babel/preset-env @babel/preset-react babel-loader

## The directory of React app 
    quantify-ass/
    ├── public/
    │   └── index.html
    ├── src/
    │   ├── App.jsx
    │   └── index.js
    ├── .babelrc
    ├── package.json
    └── webpack.config.js

## Config the file '.babelrc'
    {
      "presets": [
        "@babel/preset-env",
        "@babel/preset-react"
      ]
    }
