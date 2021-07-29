<template>
  <div id="flashMessage_Edit" v-if="GStore.flashMessage_Edit">
    {{ GStore.flashMessage_Edit }}
  </div>
  <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
  <p>{{ event.description }}</p>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore']
}
</script>

<style>
@keyframes greenfade {
  from {
    background: #4bd84b;
  }
  to {
    background: transparent;
  }
}
#flashMessage_Edit {
  animation-name: greenfade;
  animation-duration: 3s;
}
</style>