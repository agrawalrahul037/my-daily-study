# Check if the user is scrolled to the bottom of the page

   window.onscroll = () => {
      var d = document.documentElement;
      var offset = Math.floor(d.scrollTop + window.innerHeight);
      var height = d.offsetHeight;

      if (offset === height) {
        console.log('At the bottom');
      }
    }

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
   

