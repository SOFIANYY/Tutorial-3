<template>
  <HomePage />
  <BaseButton
    :disabled="isPending"
    :color="color"
    @click.stop.prevent="handleClick"
  >
    <font-awesome-icon 
      v-if="isPending"
      :icon="['fas', 'circle-notch']"
      pulse
    />
    <slot />
  </BaseButton>
</template>

<script>
import BaseButton from './components/BaseButton.vue';
import HomePage from "./components/HomePage.vue";


export default {
  name: 'AsyncButton',
  components: { 
    BaseButton,
    HomePage,
  
  },
  inheritAttrs: false,

  props: {
    color: {
      type: String,
      default: 'primary'
    }
  },

  data () {
    return {
      isPending: false,
    }
  },

  methods: {
    handleFulfilledA(){
       console.log("fullfilled")
    },
    handleRejectedA(){
        console.log("rejected")
    },
    handleClick () {
      const originalOnClick = ()=>{ /** @type {() => Promise<void>} */ (this.$attrs.onClick)}
      this.isPending = true
      const promise= new Promise((resolve) => {
        setTimeout(() => {
        resolve(originalOnClick());
        this.isPending=false;
        }, 2000);
      });
      promise.then(this.handleFulfilledA, this.handleRejectedA)
    }
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 300px;
}

</style>
