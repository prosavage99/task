<template>
  <div class="table">
    <div class="box">
      <div class="item">Название товара</div>
      <div class="item">Цвет</div>
      <div class="item">Размер</div>
      <div class="item">Доступное кол-во</div>
      <div
        class="item"
        @mouseenter="hoverClass = 'btn'"
        @mouseleave="hoverClass = ''"
        :class="hoverClass"
        @click.prevent="onPriceSort"
      >
        Цена
      </div>
    </div>
    <ItemList v-for="item in items" v-bind:key="item.id" v-bind:item="item" />
  </div>
</template>

<script>
import ItemList from "@/components/ItemList";

export default {
  name: "task",
  props: ["items"],
  data() {
    return {
      sortedPrice: true,
      hoverClass: "",
    };
  },
  methods: {
    onPriceSort() {
      if (this.sortedPrice) {
        this.items = this.items.sort((a, b) => (a.price > b.price ? 1 : -1));
        this.sortedPrice = false;
      } else {
        this.items = this.items
          .sort((a, b) => (a.price > b.price ? 1 : -1))
          .reverse();
        this.sortedPrice = true;
      }
    },
  },
  components: { ItemList },
};
</script>

<style>
.table {
  align-content: center;
  margin: auto;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: space-between;
  list-style: none;
  overflow: hidden;
}
.box {
  margin: 1px;
  padding: 0;
  display: flex;
}
.item {
  flex: 1;
  margin: auto;
  padding: 0;
}

.btn:hover {
  background-color: rgb(212, 212, 212);
}
</style>