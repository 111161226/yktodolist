<template>
  <div>
    <div>TODOリスト</div>
    <div v-for="item in items" :key="item.name">
      <div class="item" :class="{ ok: item.percent >= 100  }">
        <div class="name">タスク: {{ item.name }}</div>
        <div v-if="item.percent >= 100">完</div>
        <div v-if="item.percent < 100">未完</div>
      </div>
    </div>
    <div>
      <label>
        タスク
        <input v-model="newItemName" type="text" />
      </label>
      <label>
        状態
        <input v-model="newItemPrice" type="text" />
      </label>
      <button @click="addItem">add</button>
    </div>
  </div>
</template>
  
  <script>
  import { ref } from "vue";

  export default {
    setup() {
    const items = ref([
      { name: "TODOリスト", percent: 100 },
    ]);
    const newItemName = ref("");
    const newItempercent = ref(0);

    const addItem = () => {
      items.value.push({ name: newItemName.value, percent: newItemZyoutai.value });
    };

    return { items, newItemName, newItempercent, addItem };
  },
  };
  </script>
  
  <style>
  .ok {
  color: red;
}
  </style>