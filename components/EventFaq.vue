<template>
  <div id='faq' class='container'>
    <h2>FAQ</h2>
    <div class="items">
      <div class="item" v-for='item in faqs' :key='item.q'>
        <p><b>{{ item.q }}</b></p>
        <p>{{ item.a }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['faqs']
}
</script>

<style scoped>
#faq {
  padding-bottom: 4em;
}
h2 {
  font-size: 2em;
}
.items {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  margin-top: 1.5em;
}
.item {
  margin-bottom: 1.5em;
  margin: 1em;
  display: flex;
  flex-direction: column;
}
.item b {
  display: block;
  font-weight: bold;
  margin-bottom: 0.25em; 
}

@media screen and (max-width: 960px) {
  #faq {
    padding-bottom: 0;
  }
  h2 {
    font-size: 1.25em;
  }
  .items {
    grid-template-columns: 1fr;
  }
}
</style>
