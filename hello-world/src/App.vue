<template>
  <div>
    <div>{{ greet }} {{ name }}</div>
    <div v-html="channel"></div>
    <div v-html="hack"></div>
    <h2 v-bind:id="heading">Heading</h2>
    <button v-bind:disabled="isDisabled">Click me</button>
    <h2 class="underline">underlined text</h2>
    <h2 v-bind:class="status">Status</h2>
    <h2 v-bind:class="isPromoted && 'promoted'">Promoted movie</h2>
    <h2 v-bind:class="isSoldOut ? 'sold-out' : 'new'">Soldout? movie</h2>
    <h2 v-bind:class="['new', 'promoted']">Newly promoted movie</h2>
    <h2 v-bind:class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']">Array conditional movie</h2>
  </div>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      greet: 'Hello',
      name: "Vishwas",
      channel: "<b>Codevolution</b>",
      hack: `<a href="#" onclick="alert('you have been hacked')">Win a prize</a>`,
      headingId: 'heading',
      isDisabled: false,
      status: 'success',
      isPromoted: false,
      isSoldOut: false,
    };
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline {
  text-decoration: underline;
}

.promoted  {
  font-style: italic;
}

.new {
  color: olivedrab;
}

.sold-out {
  color: red;
}
</style>
