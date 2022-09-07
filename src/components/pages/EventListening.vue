<template>
  <div class="page-on-click">
    <h1>How about on click?</h1>

    <h3 class="data-title">Click the button! What happened?</h3>
    <div class="data-area row">
      <button class="button-on-click" @click="this.onClick">Click Me</button>
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
  methods: {
    onClick: () => {
      alert('Peekaboo!');
      console.log('console log also');

    },
    onChange: () => {
      console.log('Value is changed. You`d rather to use \'watch\' for watching value');
    },
    onKeydown: () => {
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
.page-on-click {
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
