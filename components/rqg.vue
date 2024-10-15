<template>
  <div id="main">

<div class="container">
    <h3>{{ quote }}</h3>
    <p>-{{author}}</p>
    <button @click="newQuote()">New quote</button>
</div>

  </div>
</template>

<script>
import axios from 'axios' ;
export default {
    mounted() {
    const apiUrl = 'https://quotes-api-self.vercel.app/quote'

        axios.get(apiUrl).then( 
        (response) => {
            this.quote = response.data.quote;
            this.author = response.data.author;
        }
    ).catch( 
        (error) => {
            console.error('error fetching data', error)
        }
    )
     

},
methods : {
    newQuote() {
    const apiUrl = 'https://quotes-api-self.vercel.app/quote'
    axios.get(apiUrl).then( 
        (response) => {
            this.quote = response.data.quote;
            this.author = response.data.author;
        }
    )
}
},

data() {
    return {
quote : null,
author:null
    }
}
}
</script>

<style>
#main {
    display: flex;
align-items: center;
justify-content: center;
font-family: sans-serif;
}
.container {
    border: 1px solid black;
    width: 340px;
    height:170px;
    display: block;
    align-content: center;
    text-align: center;

}
h1{
    border: 1px solid black;
}
p{
    border: 1px solid black;
}
</style>