<template>
  <div id="main">

<div class="container">
    <h1 >quote</h1>
    <p>author</p>
    <button>New quote</button>
</div>

  </div>
</template>

<script>
export default {
data() {
    return {

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