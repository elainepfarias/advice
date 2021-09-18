
<template>
<div class="geral">

  <div>
    <h1 class="tittle">Wise advice</h1>
  </div>
  <div>
    <button class="button" @click="getAdvice">Give me an advice</button>
    <div class="advice">{{ this.advice }}</div>
  </div>
</div>
</template>

<script>
import axios from "axios"

export default {
  data() {
        return {
            advice: ""
        }
    },

  methods: {
    async getAdvice() {
      const resp = await axios.get("https://api.adviceslip.com/advice");
      this.advice = resp.data.slip.advice;
    },

  }

}
</script>

<style>
.button {
  background-color: blueviolet;
  padding: 10px;
  font-size: 30px;
  border-radius: 5px;
  color: white
}
.tittle{
  padding-block-end: 40px;
  font-size: xxx-large;
  color: white;
}
.geral{
  background-color: violet;
  padding: 100px;
}
.advice{
  padding: 50px;
  padding-right: 30px;
  background-color: white;
  margin-top: 40px;
  border-radius: 5px;
  font: xxxx-large;
  color: blueviolet;
}
</style>
