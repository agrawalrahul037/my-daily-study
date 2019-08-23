# After setting value from setState(). Value is not updated
For resolve that issue you need to use callbacks
#### Problem->Without using callbacks 
```javascript
class TodoApp extends React.Component {
  constructor(props) {
    super(props)
    this.state = {
    	item: "pankaj"
    }
  }
  componentDidMount(){
   this.setState({item:"nitin"});
   console.log(this.state.item);  // output will be "pankaj"
  }
  render() {
    return (
      <div>
        <h2>Todos:</h2>
          {this.state.item}
      </div>
    )
  }
}
ReactDOM.render(<TodoApp />, document.querySelector("#app"))
```

#### Solution->When We are using callbacks then
```javascript
  componentDidMount(){
   this.setState({item:"nitin"},()=>{
   console.log(this.state.item);  // output will be "nitin"
   });
  }
```


### Example- with callback
# Using webpack config while i debug code on source tab then original JavaScript is not showing,
You need to just add below config setting in webpack.config.js file
```javascript
devtool: "source-map",
```
# Use bootstrap 4 in our react webpack babel project

first setup your project using @setting up new react project using webpack and babel  mentioned below <br>
After that follow below process <br>
install bootstrap in our project
```javascript
npm install bootstrap --save
```
install bootstrap dependencies
```javascript
npm install jquery popper.js --save
```
Then we install webpack loaders
```javascript
npm install style-loader css-loader postcss-loader precss autoprefixer sass-loader --save
```
First we import bootstrap resources in index.js
```javascript
import 'bootstrap/dist/css/bootstrap.min.css';
```
use bootstrap classes inside that <br>
Start node server <br>
```javascript
npm start
```
# setting up new react project using webpack and babel 
make any project folder
```javascript
mkdir my-webpack-project
```
initialize package.json
```javascript
npm init
```
we will install webpack and webpack-cli for module bundler and We installed webpack-cli so that we  <br>
can use webpack in the command line.
```javascript
npm install webpack webpack-cli --save-dev
```

install react
```javascript
npm install react react-dom --save
```
We need Babel to transpile ES6 and JSX to ES5. <br> 
babel-core: Transforms ES6 code to ES5 <br>
babel-loader: Webpack helper to transpile code, given the the preset. <br>
babel-preset-env: Preset which helps babel to convert ES6, ES7 and ES8 code to ES5. <br>
babel-preset-react: Preset which Transforms JSX to JavaScript. <br>
```javascript
npm install @babel/core babel-loader @babel/preset-env @babel/preset-react --save-dev
```

Create an index.js file inside root of the /src folder. This file will be the entry point to our app.
```javascript
import React from "react";
import ReactDOM from "react-dom";
import App from "./components/App.js";

ReactDOM.render(<App />, document.getElementById("root"));
```

Create an index.html file inside root of the /src folder and add following code inside it.
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>my project</title>
</head>
<body>
    <div id="root"></div>
</body>
</html>
```
Create a webpack.config.js in the root directory of the project
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
  ]
 };
```
Here babel-loader is used to load our JSX/JavaScript files and css-loader is used to load and bundle all of the CSS files <br>
into one file and style-loader will add all of the styles inside the style tag of the document.
```javascript
npm install css-loader style-loader --save-dev
```

Create an App.js file inside the components folder of the src folder with the following contents inside of it.
```javascript
import React, { Component } from "react";
import '../styles/App.css';
class App extends Component {
    render() {
        return (
            <div>
                <h1>My React App! </h1>
                <p className="text-hide">Hello one1234</p>
				<img src="media/images/abc.png"></img>
            </div>
        );
    }
}
export default App;
```

Create an App.css file inside the styles folder of the src folder with the following contents inside of it.
```javascript
h1 {
    color: #27aedb;
    text-align: center;
}
```
Now we also need to install html-webpack-plugin, this plugin generates an HTML file, injects the script inside the <br>
HTML file and writes this file to dist/index.html
```javascript
npm install html-webpack-plugin --save-dev
```

Install webpack-dev-server as a dev-dependency as to auto refresh changes 
```javascript
npm install webpack-dev-server --save-dev
```
And change the package.json start script like below: <br>
I have added two flags --open and --hot which opens and refreshes the web page whenever any change is made to components
```javascript
"start": "webpack-dev-server --mode development --open --hot"
"build": "webpack --mode production"
```
Now run the below command in the terminal:
```javascript
npm start
```
And for build run below command
```javascript
npm run build
```

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
   
--------------------------------------------------------------------------------------------------------------------
For Above code and solution I took help from so many internet resource and my friends <br>
Special Thank to <br>
-> Indrajeet Gupta <br>
-> Piyush Rathi

