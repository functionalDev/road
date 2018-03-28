<template>
  <div tabindex="-1" :style="randomBackground">
    <div class="hover">
      hover
    </div>
    <div class="text">
      {{ element }}
    </div>
    <div class="focus">
      {{ element }}
    </div>
    <div class="overlay">
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
      console.log(this.element, hex);
      return {
        background: `#${hex.toString(16).substr(-6)}FF`,
        color: '#FFFFFF',
        'grid-area': this.element,
      };
    },
  },
};
</script>

<style scoped>
.block > * {
  padding: 5px;

}
.text {
  z-index: 10;
}
.block {
  border: 1px solid rgba(0, 0, 0, 0.2);
  /* background-color: 1px solid rgba(0, 0, 0, 0.2); */
  padding-top: 5px;
  /* position: relative; */
}
.hover {
  opacity: 0;
  position: absolute;
  transition: all 0.2s;
  left: 0;
}
.focus {
  opacity: 0;
  position: absolute;
  transition: all 0.2s;
  right: 0;
}
.block:hover .hover{
  opacity: 1;
}
.block:focus .focus{
  opacity: 1;
}
.block:focus{
  box-shadow: 1px 1px 1px 1px rgba(0, 0, 0, 0.5);
}
.browser {
}
.webApp {
  grid-column-start: 10;
  grid-column-end: 12;
  grid-row-start: 5;
}
.webApi {
  grid-column-start: 10;
  grid-column-end: 12;
  grid-row-start: 7;
}
.PSS {
  grid-column-start: 10;
  grid-column-end: 12;
  grid-row-start: 9;
}
.psssearch {
  grid-column-start: 10;
  grid-column-end: 12;
  grid-row-start: 11;
}
.redis1 {
  grid-column-start: 8;
  grid-column-end: 9;
  grid-row-start: 5;
}
.redis2 {
  grid-column-start: 8;
  grid-column-end: 9;
  grid-row-start: 7;
}
.cssearch {
  grid-column-start: 14;
  grid-column-end: 16;
  grid-row-start: 11;
}
.COS {
  grid-column-start: 14;
  grid-column-end: 16;
  grid-row-start: 8;
}
.CDA {
  grid-column-start: 14;
  grid-column-end: 16;
  grid-row-start: 6;
}
.CMS {
  grid-column-start: 16;
  grid-column-end: 17;
  grid-row-start: 8;
}
</style>
