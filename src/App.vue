<template>
  <div id="app" class="container">
    <h2>{{ title }}</h2>
    <add-item-component @accessAddItem="addItem">
    </add-item-component>
    <items-component :items="items">
    </items-component>
    <div class="footer">
      <hr/>
      <change-title-component
        @changeNewTitle="changeNewTitle">
      </change-title-component>
    </div>
  </div>
</template>

<script>
import AddItemComponent from './components/AddItemComponent.vue'
import ItemsComponent from './components/ItemsComponent.vue'
import ChangeTitleComponent from './components/ChangeTitleComponet.vue'
export default {
  components: {
    AddItemComponent,
    ItemsComponent,
    ChangeTitleComponent
  },
  data: function () {
    return {
      items: [
        {text: 'Bananas', checked: true},
        {text: 'Appels', checked: false}
      ],
      title: 'Shopping List',
      newItem: ''
    }
  },
  methods: {
    addItem: function (payload) {
      this.items.push({
        text: payload.text,
        checked: payload.checked
      })
    },
    changeNewTitle: function (payloader) {
      this.title = payloader.title
    }
  }
}
// todo : Create add item     STATUS - DONE
// todo : and change title      STATUS - DONE
// todo : Create documentation  STATUS - WAIT-LIST
// todo : Create animation
</script>
<style>

</style>
