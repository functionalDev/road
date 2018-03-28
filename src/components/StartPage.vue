<template>
  <div class="">
    <h1>{{ msg }}</h1>
    <div class="architecture">
      <div is="Block" v-for="element in elements" :element="element" :class="`${element} block`">
      </div>
    </div>
  </div>
</template>

<script>
import Block from './Block';

export default {
  name: 'hello',
  data() {
    return {
      msg: 'ROAD',
      elements: ['browser', 'webCache', 'webApp', 'webApi', 'redis1', 'redis2', 'PSS', 'psssearch', 'COS', 'cssearch', 'CDA'],
    };
  },
  components: {
    Block,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
.architecture {
  display: grid;
  /* grid-template-columns: repeat(20, 1fr);
  grid-template-rows: 1fr 1fr 25px repeat(9, 1fr); */
  position: relative;
  background: url('../../static/img/bg.png');
  background-size: 100% 100%;
  width: 80vw;
  height: 75vh;
  margin: 0 10vw;
  border: 1px solid rgba(0, 0, 0, 0.2);
  grid-gap: 50px 100px;
  grid-template-areas:
    ".  .       browser   .   ."
    ".  .       webCache  .   ."
    ".  redis1  webApp    CDA ."
    ".  redis2  webApi    .   ."
    ".  .       PSS       COS ."
    ".  .       psssearch cssearch .";
}
</style>
