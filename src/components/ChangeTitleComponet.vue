<template>
  <div class="row">
    <div class="col-lg-5">
      <div class="input-group">
        <input type="text" class="form-control"
               placeholder="Change Title"
               v-model="newTitle"
               @keyup.enter="changeTitle">
        <span class="input-group-btn">
        <button type="button" class="btn btn-danger"
                :value="newTitle"
                @click="changeTitle">Change!
        </button>
      </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      newTitle: ''
    }
  },
  methods: {
    changeTitle: function (e) {
      this.newTitle = e.target.value.trim()
      if (this.newTitle) {
        /*
          | Event $emit communication
          | between parent methods
        */
        this.$emit('changeNewTitle', {
          title: this.newTitle
        })
      }
      this.newTitle = ''
    }
  }
}
</script>

<style scoped>

</style>
