<template>
  <div class="page-modals">
    <h1>Let's control modals</h1>

    <h3 class="data-title">Click the button to display modal!</h3>
    <div class="data-area row">
      <button class="button-on-click" @click="this.onClick">Basic Modal</button>
    </div>

    <h3 class="data-title">Logging on console when value changing</h3>
    <div class="data-area row">
      <input @change="this.onChange" placeholder="Change">
    </div>

    <h3 class="data-title">Logging on console when keypress</h3>
    <div class="data-area row">
      <input @keydown="this.onKeydown" placeholder="keydown">
    </div>

  </div>
  <BasicModal v-if="this.basicModalDisplay"></BasicModal>
</template>

<script>
import BasicModal from '@/components/modals/BasicModal';

export default {
  name: 'PageDataBind',
  data() {
    return {
      basicModalDisplay: false
    }
  },
  components: {
    BasicModal,
  },
  methods: {
    onClick()  {
      this.basicModalDisplay = true;
    },
    onChange() {
      console.log('Value is changed. You`d rather to use \'watch\' for watching value');
    },
    onKeydown() {
      console.log('What is difference between change and keydown');
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
.page-modals {
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


.button-on-click {
  padding: 8px;
}
</style>
