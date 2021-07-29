<template>
  <p>Edit the event here</p>
  <button @click="edit">Edit Me</button>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore'],
  methods: {
    edit() {
      //Assuming successful API call to edit them
      //Set a flash message to appear on the next page loaded which says
      //'The data has been updated for ' + this.event.title

      this.GStore.flashMessage_Edit =
        'The data has been updated for ' + this.event.title
      setTimeout(() => {
        //After 3 seconds remove it
        this.GStore.flashMessage_Edit = ''
      }, 3000)

      this.$router.push({
        name: 'EventDetails',
        params: { id: this.event.id }
      })
    }
  }
}
</script>
