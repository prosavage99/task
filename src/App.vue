<template>
  <div id="app">
    <h1>Task application</h1>
    <hr />
    <select v-model="filter">
      <option value="all">All</option>
      <option value="s">S</option>
      <option value="m">M</option>
      <option value="l">L</option>
      <option value="xl">XL</option>
      <option value="xxl">XXL</option>
    </select>
    <Task v-bind:items="sizeFilterItems" />
  </div>
</template>
<script>
import Task from "@/components/Task";
export default {
  name: "app",
  data() {
    return {
      filter: "all",
      items: [
        {
          id: 1,
          title: "Товар 1",
          color: "red",
          colorValue: "#FF004D",
          size: "S",
          amount: 26,
          price: 900,
        },
        {
          id: 2,
          title: "Товар 1",
          color: "red",
          colorValue: "#FF004D",
          size: "M",
          amount: 24,
          price: 940,
        },
        {
          id: 3,
          title: "Товар 1",
          color: "red",
          colorValue: "#FF004D",
          size: "L",
          amount: 12,
          price: 300,
        },
        {
          id: 4,
          title: "Товар 1",
          color: "red",
          colorValue: "#FF004D",
          size: "XL",
          amount: 32,
          price: 800,
        },
        {
          id: 5,
          title: "Товар 2",
          color: "green",
          colorValue: "#008365",
          size: "M",
          amount: 9998,
          price: 200,
        },
        {
          id: 6,
          title: "Товар 2",
          color: "green",
          colorValue: "#008365",
          size: "L",
          amount: 45,
          price: 230,
        },
        {
          id: 7,
          title: "Товар 2",
          color: "green",
          colorValue: "#008365",
          size: "XXL",
          amount: 1,
          price: 1300,
        },
        {
          id: 8,
          title: "Товар 3",
          color: "blue",
          colorValue: "#3B5998",
          size: "S",
          amount: 0,
          price: 0,
        },
        {
          id: 9,
          title: "Товар 3",
          color: "blue",
          colorValue: "#3B5998",
          size: "M",
          amount: 0,
          price: 0,
        },
        {
          id: 10,
          title: "Товар 3",
          color: "mars",
          colorValue: "#3B5998",
          size: "L",
          amount: 23,
          price: 130,
        },
        {
          id: 11,
          title: "Товар 4",
          color: "mars",
          colorValue: "#4C1A2C",
          size: "L",
          amount: 0,
          price: 0,
        },
        {
          id: 12,
          title: "Товар 4",
          color: "mars",
          colorValue: "#4C1A2C",
          size: "XL",
          amount: 0,
          price: 0,
        },
        {
          id: 13,
          title: "Товар 4",
          color: "mars",
          colorValue: "#4C1A2C",
          size: "XXL",
          amount: 0,
          price: 0,
        },
      ],
    };
  },
  computed: {
    sizeFilterItems() {
      if (this.filter === "all") {
        return this.items;
      }

      if (this.filter === "s") {
        return this.items.filter((t) => t.size === "S");
      }

      if (this.filter === "m") {
        return this.items.filter((t) => t.size === "M");
      }
      if (this.filter === "l") {
        return this.items.filter((t) => t.size === "L");
      }

      if (this.filter === "xl") {
        return this.items.filter((t) => t.size === "XL");
      }

      if (this.filter === "xxl") {
        return this.items.filter((t) => t.size === "XXL");
      }
    },
  },
  components: {
    Task,
  },
};
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
