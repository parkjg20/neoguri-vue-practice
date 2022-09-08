<template>
  <div class="basic-modal-backdrop">
    <button class="button-close">X</button>
    <div class="basic-modal-content">
      <h3>{{ title }}</h3>
      <p>{{ message }}</p>
      <div class="basic-modal-buttons">
        <button class="positive-button" @click="this.onPositiveCallback">OK</button>
      </div>
    </div>

  </div>
</template>

<script>

export default {
  name: 'PageDataBind',
  props: {
    title: String,
    message: String,
    positiveCallback: Function
  },
  data() {
    return {

    }
  },
  methods: {
    onPositiveCallback: () => {
      if (typeof this.positiveCallback === 'function') {
        this.positiveCallback()
      }

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

.basic-modal-backdrop {
  z-index: 1;
  width: 100vw;
  height: 100vh;

  position:fixed;
  top: 0;
  left: 0;

  padding-top: 32px;
  background-color: rgba(0, 0, 0, 0.65);

  justify-content: center;
  align-items: center;
}

.button-close {
  width: 24px;
  height: 24px;
  position: absolute;

  top: 4px;
  right: 4px;
}

.basic-modal-content {
  flex-direction: column;
  background-color: #F4F4F4;
  padding: 32px 16px;
}



</style>
