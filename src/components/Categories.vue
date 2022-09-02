<template>
  <div class="categories">
    <ul>
      <li v-for="category in categories" :key="category.id" :class="{active: active === category.id}" @click="active = category.id">{{ category.name }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "CategoriesComponent",
  data() {
    return {
      active: 0,
      categories: [
        {
          id: 0,
          name: 'Все',
        },
        {
          id: 1,
          name: 'Мясные',
        },
        {
          id: 2,
          name: 'Вегетарианская',
        },
        {
          id: 3,
          name: 'Гриль',
        },
        {
          id: 4,
          name: 'Острые',
        },
        {
          id: 5,
          name: 'Закрытые',
        },
      ],
    };
  },
}
</script>

<style scoped>

</style>