<template>
  <div>
    <div>{{ greet }} {{ name }}</div>
    <div v-html="channel"></div>
    <div v-html="hack"></div>
    <h2  :id="heading">Heading</h2>
    <button  :disabled="isDisabled">Click me</button>
    <h2 class="underline">underlined text</h2>
    <h2  :class="status">Status</h2>
    <h2  :class="isPromoted && 'promoted'">Promoted movie</h2>
    <h2  :class="isSoldOut ? 'sold-out' : 'new'">Soldout? movie</h2>
    <h2  :class="['new', 'promoted']">Newly promoted movie</h2>
    <h2  :class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']">Array conditional movie</h2>
    <h2  :style="{
      color: highlightColor,
      'font-size': headersize + 'px',
      padding : '20px',
      }">Inline style</h2>
      <h2  :style="headStyleObject">style object</h2>
  
  <div  :style="[baseStyleObject, successStyleObject]">success style</div>
  <div  :style="[baseStyleObject, dangerStyleObject]">danger style</div>
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
      highlightColor: 'orange',
      headersize: '50',
      headStyleObject: {
        color: 'orange',
        fontSize: '50px',
        padding: '20px',
      },
      baseStyleObject:{
        fontSize: '50px',
        padding: '10px',
      },
      successStyleObject: {
        color: 'blueviolet',
        backgroundColor: 'lightblue',
        border: '1px solid black',

      },
      dangerStyleObject: {
        color:'red',
        backgroundColor: 'lightcoral',
        border: '1px solid black',
      },
    }
  },

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
