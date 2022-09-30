<template>
  <q-img class="stretch" src="yaar.jpeg" @click="onClick">
    <div class="absolute-top text-subtitle1 text-center">
      מפת השטח
    </div>
  </q-img>
</template>

<script lang="ts">
export default {
  setup () {
    function onClick() {
      window.location.href = 'yaar.jpeg'
    }

  return { onClick }
},
}
</script>
