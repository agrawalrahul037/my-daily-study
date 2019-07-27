# Setting up new react project

```javascript
npx create-react-app my-app
cd my-app
npm start
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
   

