<template>
  <div id="main">
    <div id="quote-box">
      <h3 id="text">{{ quote }}</h3>
      <p id="author">-{{ author }}</p>
      <button id="new-quote" @click="newQuote()">New quote</button>
      
      <a id="tweet-quote" :href="xurl"
        >tweet</a>
      
    </div>
  </div>
</template>
<script>
import axios from "axios";

export default {
  mounted() {
    const apiUrl = "https://quotes-api-self.vercel.app/quote";
    axios
      .get(apiUrl)
      .then((response) => {
        this.quote = response.data.quote;
        this.author = response.data.author;
      })
      .catch((error) => {
        console.error("error fetching data", error);
      });
  },
  methods: {
    newQuote() {
      const apiUrl = "https://quotes-api-self.vercel.app/quote";
      axios.get(apiUrl).then((response) => {
        this.quote = response.data.quote;
        this.author = response.data.author;
      });
    },

  },
  data() {
    return {
      quote: null,
      author: null,
    };
  },
  computed :{
    xurl(){
return "https://twitter.com/intent/tweet?text=" + this.quote 
}
  }
};
</script>

<style>
#main {
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: sans-serif;
  margin-top: 48px;
}
#quote-box {

  width: 340px;
  height: 170px;
  display: block;
  align-content: center;
  text-align: center;
}
#text {

}
#author {

}
#tweet-quote {
}
</style>
