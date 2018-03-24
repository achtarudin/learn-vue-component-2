<template>
  <div class="row">
    <div class="col-lg-5">
      <div class="input-group">
        <input type="text" class="form-control"
               placeholder="add shopping list"
               v-model="inputNewItem"
               @keyup.enter="addNewItem">
        <span class="input-group-btn">
        <button type="button" class="btn btn-primary"
                :value="inputNewItem"
                @click="addNewItem">Add
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
      inputNewItem: ''
    }
  },
  methods: {
    addNewItem: function (e) {
      this.inputNewItem = e.target.value.trim()
      if (this.inputNewItem) {
        /*
          | Event $emit communication
          | between child methods to parent methods
        */
        this.$emit('accessAddItem', {
          text: this.inputNewItem,
          checked: false
        })
        this.inputNewItem = ''
      }
    }
  }
}
</script>

<style>

</style>
