<template>
  <div>
    <svg
      width="300"
      height="100"
    >
      <circle
        cx="50"
        cy="50"
        r="40"
        class="light-blob"
        :fill="colorBefore"
      />
      <circle
        cx="150"
        cy="50"
        r="40"
        class="light-blob"
        :fill="colorAfter"
      />
    </svg>
    <br>
    <svg
      width="200"
      height="100"
      class="back"
    >
      <path
        d="m0 50 l200 0"
        :stroke="startComp"
        stroke-width="10"
      />
    </svg>
    <svg
      width="25"
      height="100"
      class="back"
    >
      <rect
        width="25"
        height="100"
        rx="5"
        ry="5"
        fill="black"
        stroke-width="0"
      />
      <text
        x="2"
        y="54"
        fill="white"
      >Op</text>
    </svg>
    <svg
      width="200"
      height="100"
      class="back"
    >
      <path
        d="m0 50 l200 0"
        :stroke="abc"
        stroke-width="10"
      />
    </svg>
  </div>
</template>

<script lang="ts">


function giveColor(arr){
  const a = arr.map((d) => Math.round(d * 255));
  return `rgb(${a.join(',')})`;
}

export default  {
  components: {
  },
  props: {
    hover: Array,
    leftBeam: Array

  } ,
      

  data: function() {
      return {
      colorAfter: giveColor(this.hover),
      colorBefore: giveColor(this.leftBeam)
  }},
  methods: {}
}

</script>

<style>
.light-blob {
    opacity: 0.2
}
.light-blob:hover {
    opacity: 1 
}
.back {
  background-color:#00ccff
}

</style>