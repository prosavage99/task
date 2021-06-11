<template>
  <div class="box">
    <div class="item">
      {{ item.title }}
    </div>
    <div
      class="item"
      v-bind:style="{ backgroundColor: item.colorValue, color: 'white' }"
    >
      {{ item.color }}
    </div>
    <div class="item">{{ item.size }}</div>
    <div class="item">{{ item.amount }}</div>
    <div class="item">{{ item.price }}</div>
  </div>
</template>

<script>
export default {
  name: "itemlist",
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
};
</script>

