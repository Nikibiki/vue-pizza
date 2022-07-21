<template>
  <div class="wrapper">
    <HeaderComponent/>
    <div class="content">
      <div class="container">
        <div class="content__top">
          <CategoriesComponent />
          <SortComponent />
        </div>
        <h2 class="content__title">Все пиццы</h2>
        <div class="content__items">
          <PizzaBlock title="Простая пицца" :price="399"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import HeaderComponent from "@/components/Header";
import CategoriesComponent from "@/components/Categories"
import SortComponent from "@/components/Sort"
import PizzaBlock from "@/components/PizzaBlock"

export default {
  name: "App",
  components: {
    HeaderComponent,
    CategoriesComponent,
    SortComponent,
    PizzaBlock
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
