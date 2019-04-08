<template>
  <div class="">
    <h1 @click="complete = !complete">{{ msg }}</h1>
    <div :class="`architecture ${complete}`">
      <div is="Block" v-for="element in elements" :element="element" :class="`${element.type} ${element.class} ${element.complete} block`">
      </div>
    </div>
  </div>
</template>

<script>
import Block from './Block';
import { systems } from '../systems.json';

export default {
  name: 'hello',
  data() {
    return {
      msg: 'ROAD',
      elements: systems,
      complete: false,
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
  /* font-weight: normal; */
  text-align: 30%;

}
.architecture {
  display: grid;
  /* grid-template-columns: repeat(20, 1fr);
  grid-template-rows: 1fr 1fr 25px repeat(9, 1fr); */
  position: relative;
  max-width: 1024px;
  background: url('../../static/img/bg_incomplete.png');
  background-size: 100% 100%;
  width: 80vw;
  /* height: 75vh; */
  margin: 0 auto;
  border: 1px solid rgba(0, 0, 0, 0.5);
  padding: 15px;
  grid-gap: 50px 100px;
  grid-template-areas:
    ".       browser   .   ."
    ".       webCache  .   ."
    ".       webApp    CDA ."
    "redis1  webApi    .   CMA"
    "redis2  PSS       COS ."
    ".       psssearch cssearch .";
}
.architecture.true {
  background: url('../../static/img/bg_complete.png');
  background-size: 100% 100%;
}
</style>
