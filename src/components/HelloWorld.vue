<template>
  <div>
    <h1>{{ msg }}</h1>
    <counter />
  </div>
</template>

<script>
import Counter from "./Counter.vue";
import ItemList from "./ItemList.vue";

export default {
  components: {
    Counter,
    ItemList,
  },
  props: {
    msg: {
      type: String,
      default: "",
    }
  },
};
</script>