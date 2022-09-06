<template>
  <div class="page-data-bind">
    <h1>Data Bind Practice</h1>

    <h3 class="data-title">Model, synchronize between input value and data variable</h3>
    <div class="data-area row">
      <input v-model="modelText">

      <p class="data-bind-target">{{ modelText }}</p>
    </div>

    <h3 class="data-title">Computed, run computing function and return when data change detected.</h3>
    <div class="data-area row">
      <input v-model="watchText">

      <p class="data-bind-target">{{ (this.watchLength > 10) ? 'length greater than 10' : 'length less than equal 10' }}</p>
    </div>

  </div>
</template>

<script>
export default {
  name: 'PageDataBind',
  data() {
    return {
      modelText: 'modelText',
      watchText: 'watchText'
    }
  },
  watch: {
    watchText(value) {
      console.log('value has been changed', value);
    }
  },
  computed: {
    watchLength() {
      return this.watchText.length;
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.page-data-bind {
  flex-direction: column;
}

.data-title {
  font-size: 20px;
  font-weight: bold;
}

.data-area {
  margin-top: 8px;
  margin-bottom: 12px;

  justify-content: center;
}

.data-bind-target {
  margin-left: 16px;
}

</style>
