
<template>
  <div>
    <h1>Wise advice</h1>
  </div>
  <div>
    <button class="bg-red-500" @click="getAdvice">Give me an advice</button>
    <div>{{ this.advice }}</div>
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

<!-- <style>

</style> -->
