<template>
  <div class="sort">
    <div class="sort__label">
      <svg
          width="10"
          height="6"
          viewBox="0 0 10 6"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
      >
        <path
            d="M10 5C10 5.16927 9.93815 5.31576 9.81445 5.43945C9.69075 5.56315 9.54427 5.625 9.375 5.625H0.625C0.455729 5.625 0.309245 5.56315 0.185547 5.43945C0.061849 5.31576 0 5.16927 0 5C0 4.83073 0.061849 4.68424 0.185547 4.56055L4.56055 0.185547C4.68424 0.061849 4.83073 0 5 0C5.16927 0 5.31576 0.061849 5.43945 0.185547L9.81445 4.56055C9.93815 4.68424 10 4.83073 10 5Z"
            fill="#2C2C2C"
        />
      </svg>
      <b>Сортировка по:</b>
      <span @click="isVisible = !isVisible">{{selectedFilter}}</span>
    </div>
    <div class="sort__popup" v-if="isVisible">
      <ul>
        <li v-for="sort in orderBy" :key="sort.id" :class="{active: active === sort.id}" @click="switchAndClose(sort.id)">{{ sort.name }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "SortComponent",
  data(){
    return {
      isVisible: false,
      active: 0,
      orderBy: [
        {
          id: 0,
          name: 'популярности'
        },
        {
          id: 1,
          name: 'цене'
        },
        {
          id: 2,
          name: 'алфавиту'
        },
      ],
    };
  },
  computed: {
    selectedFilter(){
      const active = this.active;
      return this.orderBy.filter(elem => elem.id === active).pop().name;
    }
  },
  methods: {
    switchAndClose(index) {
      this.active = index;
      this.isVisible = false;
    }
  },
}
</script>

<style scoped>

</style>