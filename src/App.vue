<template>
  <div id="app">
    <header-component :msg="titolo"/>
    <main>
      <app-grid/>
    </main>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import AppGrid from './components/AppGrid.vue';


export default {
  name: 'App',
  components: {
    HeaderComponent,
    AppGrid
  },
  data(){
    return {
      titolo: 'Rick e Morty'
    }
  }
}
</script>

<style lang="scss">
  @import '@/style/general.scss';
</style>
