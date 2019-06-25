<template>
  <div>
    <button @click="onLoading" type="button">
      LOADING ON
    </button>
    <Spinner v-if="isLoading" />
  </div>
</template>

<script>
import Spinner from './components/Spinner'

export default {
  name: 'app',
  components: {
    Spinner
  },
  data: function () {
    return {
      isLoading: false
    }
  },
  methods: {
    onLoading: function () {
      this.isLoading = true;
    },
    offLoading: function () {
      this.isLoading = false;
    }
  },
  mounted () {
    document.body.addEventListener('keyup', e => {
      // ESC
      if (e.keyCode === 27) {
        this.offLoading();
      }
    });
  }
}
</script>

<style scoped>
  hr {
    border: 0;
    border-top: 1px solid #ddd;
    margin: 1rem 0;
  }
</style>
