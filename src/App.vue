<template>
  <div id="app">
    <h1>Heroes</h1>
    <Heroes v-bind:heroes="heroes"/>
  </div>
</template>

<script>
import { HeroService } from './heroService.js'
import Heroes from './components/Heroes.vue'

export default {
  name: 'app',
  components: {
    Heroes
  },
  data: function() {
    return {
      heroes: []
    }
  },
  created: function() {
    new HeroService().getHeroes()
      .subscribe(heroes => this.heroes = heroes);
  }
}
</script>

<style>
</style>
