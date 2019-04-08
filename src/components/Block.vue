<template>
  <div tabindex="-1" :style="randomBackground">
    <div v-for="software in element.lines" class="text">
      {{ software }}
    </div>
    <div class="focus">
      <h4>{{ element.name }}</h4>
      <div v-for="el in element.content" class="">
        {{ el }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'hello',
  props: ['element'],
  data() {
    return {
      msg: 'ROAD',
    };
  },
  computed: {
    randomBackground() {
      const hex = Math.floor(Math.random() * 0xFFFFFF);
      return {
        'grid-area': this.element.class,
      };
    },
  },
};
</script>

<style scoped>
h4 {
  text-align: center;
}
.false .incomplete {
  opacity: 0.5;
}
.block > * {
  padding: 5px;
}
.server {
  background-color:  #b2df8a;
}
.cache {
  background-color: #fb9a99;
}
.service {
  background-color: #33a02c;
}
.elasticsearch {
  background-color: #fdbf6f;
}
.browser {
  background-color: #a6cee3;
}
.text {
  z-index: 10;
  font-weight: bold;
}
.text ~ .text {
  border-top: 1px solid black;
}
.block {
  /* background-color: 1px solid rgba(0, 0, 0, 0.2); */
  padding-top: 5px;
  border: 1px solid black;
  border-bottom: 1px solid black;
  display: inline-table;
  /* position: relative; */
}
.focus > * {
  padding: 5px 0;
  margin: 0;
}
.focus {
  min-width: 200px;
  opacity: 0;
  position: absolute;
  transition: all 0.2s;
  left: 0;
  text-align: left;
  margin: 20px;
  padding: 10px;
  border: 1px solid rgba(0, 0, 0, 0.2);
  background-color: #fff59d;
  background: linear-gradient( #fff59d, #fdbf6f);
  box-shadow: 1px 1px 1px 1px rgba(0, 0, 0, 0.5);
}
.block:hover .hover{
  opacity: 1;
}
.block:focus .focus{
  opacity: 1;
  z-index: 100;
}
.block:focus{
  box-shadow: 1px 1px 2px 2px rgba(0, 0, 0, 0.7);
}
</style>
