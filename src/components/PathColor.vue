<template>
  <div class="row">
    <template v-for="n in numPairs" :key="n">
      <div
        class="col"
        :style="{'background-color': color1, minWidth: sectionWidth}"
      >
        &nbsp;
      </div>
      <div>
        &nbsp;
      </div>
      <div
        v-if="n !== numPairs || showLastColor"
        class="col"
        :style="{'background-color': color2, minWidth: sectionWidth}"
      >
        &nbsp;
      </div>
      <div
        v-if="n !== numPairs || showLastColor"
      >
        &nbsp;
      </div>
    </template>
  </div>
</template>

<script>

export default {
  setup () {
    return {}
  },
  props: {
    color1: {
      type: String,
      required: true
    },
    color2: {
      type: String,
      required: true
    },
    sectionWidth: {
      type: String,
      default: '20px'
    },
    length: {
      type: Number,
      default: 5
    }
  },
  computed: {
    numPairs () {
      return Math.ceil(this.length/2)
    },
    showLastColor () {
      return this.length % 2 === 0
    }
  }
}
</script>
