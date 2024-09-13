<template>
  <div>
    <!-- for basic UI -->

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
  
  <!-- for v-if and v-else -->

  <h2 v-if="num === 0">num is zero</h2>
  <h2 v-else-if="num > 0">num is positive</h2>
  <h2 v-else-if='num < 0'>num is negative</h2>
  <h2 v-else>not a number</h2>
  <template v-if="display">
    <h2>Hello World</h2>
    <p>This is a paragraph</p>
  </template>
  <h2 v-show="showelement">using v-show</h2>

  <!-- for v-for -->
   <h2 v-for="(name, index) in names" :key="name"> {{ index }} {{ name }}</h2>
   <h2 v-for="(name, index) in fullNames" :key="name"> {{ index }} {{ name.first }} {{ name.last }}</h2>
   <div v-for="actor in actors" :key="actor">
    <h2>{{ actor.name }}</h2>
    <h3 v-for="movie in actor.movies" :key="movie"> {{ movie }}</h3>
   </div>
   <!-- for shuffle -->
    <template v-for="name in names">
    <div :key="name">
      <h2>{{ name }}</h2>
      <input placeholder="Last name" />
      <hr />
    </div>
    </template>
    <button @click="shuffle">Shuffle!</button>
</div>
  
</template>

<script>

import _ from 'lodash';
export default {
  name: 'App',
  data() {
    return {
      // for v-for
      names: ['John', 'Jane', 'Doe', 'Smith'],
      fullNames: [
        {first: 'John', last: 'Wayne'},
        {first: 'Jane', last: 'Eyre'},
        {first: 'Doe', last: 'Lopez'},
        {first: 'Smith', last: 'Johnson'},
      ],
      actors: [
        {
          name: 'Christian Bale',
          movies: ['Batman', 'The Dark Knight', 'The Dark Knight Rises'],
        },
        {
          name: 'Leonardo DiCaprio',
          movies: ['Titanic', 'Inception', 'The Wolf of Wall Street'],
        },
      ],
      // for v-if and v-else
      display: true,
      num:5,
      showelement: true,
      // for basic UI
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
  methods: {
    shuffle() {
      console.log(this.names);
      this.names=_.shuffle(this.names);
    }
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
