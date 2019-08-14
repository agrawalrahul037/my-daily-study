# Change default 8080 port to any port using webpack.config.js file

  devServer: {
	port: 4000,
  }
  
  complete webpack.config.js file below
  ```javascript
  const path = require("path");
  const HtmlWebpackPlugin = require("html-webpack-plugin");

module.exports = {
  entry: "./src/index.js",
  output: {
    path: path.join(__dirname, "/dist"),
    filename: "index-bundle.js"
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: ["babel-loader"]
      },
      {
        test: /\.css$/,
        use: ["style-loader", "css-loader"]
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: "./src/index.html"
    })
  ],
  devServer: {
	port: 4000,
  }
 };
```
  
  
# Split bundling in react-redux project

https://github.com/maitojepoy/react-redux-loadables

# When to use react context-api AND when to use redux

conclusion-> when application is large then use redux and (when application scope is fix and for small application use context-api)  

https://daveceddia.com/context-api-vs-redux/

# Build a React project from scratch using Webpack 4 and Babel and bootstrap

```javascript
  // implementing Babel webpack
  https://hackernoon.com/how-to-build-a-react-project-from-scratch-using-webpack-4-and-babel-56d4a26afd32
  // implementing bootstrap 4
  https://medium.com/@dinyangetoh/getting-started-with-react-webpack-and-bootstrap-27e95ff634ef
  //Extracting bootstrap files from bundle file
  https://medium.com/riow/webpack-separate-css-5d1c1e862d93
```  

# Setting up new react project

```javascript
npx create-react-app my-app
cd my-app
npm start

OR
npm install -g create-react-app
```

# Add local Repository on GitHub using git command 

1- Create a new repository on GitHub. To avoid errors, do not initialize the new repository with README, license, or gitignore files
2- Open Git Bash
3- initialize local directory
    git init
4- For adding file in your local Repo
   git add .
5- For commiting files
   git commit -m "put comment here"
6- Getting remote repo url
 
7- add url for sinking with remote repository
   git remote add origin "remore repo url"
8- Push changes local to git hub
   git push origin master

# Check if the user is scrolled to the bottom of the page

   ```javascript
   window.onscroll = () => {
      var d = document.documentElement;
      var offset = Math.floor(d.scrollTop + window.innerHeight);
      var height = d.offsetHeight;

      if (offset === height) {
        console.log('At the bottom');
      }
    }
    
  ```

# How to make mock api url

https://www.mocky.io/ 


# fetch vs axios
   
    fetch("http://www.mocky.io/v2/5d348f312e00008138a6b7b2").then(response => {
      return response.json();
    }).then(myjson => {
      this.setState({
        data:myjson
      })
    })
    --------------------------------------------------------------------------------------
    axios.get("http://www.mocky.io/v2/5d348f312e00008138a6b7b2").then(response => {
       this.setState({
        data: response.data
       })
    })
   

