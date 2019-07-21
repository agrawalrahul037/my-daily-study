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

