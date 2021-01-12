<template>
  <div class="home">
    <div class="input-wrapper">
      <label>Max kcal</label>
      <input type="number" v-model="maxKcal" />
    </div>
    <div class="input-wrapper">
      <label>białko</label>
      <input type="number" v-model="proteinGrams" />
    </div>
    <div class="input-wrapper">
      <label>tłuszcz</label>
      <input type="number" v-model="fatGrams" />
    </div>
    <div class="input-wrapper">
      <label>cukry</label>
      <input type="number" v-model="carbGrams" />
    </div>
    <hr>
    <div class="input-wrapper">
      <label>Pozostało:</label>
      <h4>{{ leftKcal }}</h4>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  data() {
    return {
      maxKcal: 1200,
      fatGrams: 0,
      proteinGrams: 1,
      carbGrams: 0,
    };
  },
  computed: {
    leftKcal() {
      return this.maxKcal - (this.fatGrams * 9 + 4 * this.proteinGrams + this.carbGrams * 4);
    },
  },
};
</script>

<style lang="scss" scoped>
.input-wrapper {
  display: flex;
}
</style>
