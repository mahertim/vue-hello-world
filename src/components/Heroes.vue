<template>
  <div>
    <ul class="heroes">
      <li v-for="hero in heroes" v-bind:key="hero.id" v-on:click="selectHero(hero)" v-bind:class="{ selected: hero === selectedHero}">
        <span class="badge">{{ hero.id }}</span> {{ hero.name }}
      </li>
    </ul>
    <HeroDetail v-if="selectedHero.id" v-bind:hero="selectedHero"/>
  </div>
</template>

<script>
import HeroDetail from './HeroDetail.vue'
import { Hero } from '../hero'

export default {
  name: 'Heroes',
  components: {
    HeroDetail
  },
  props: {
    heroes: Array
  },
  data: function() {
    return {
      selectedHero: new Hero(),
    }
  },
  methods: {
    selectHero: function(hero) {
      this.selectedHero = hero;
    }
  }
}
</script>

<style>
/* HeroesComponent's private CSS styles */
.selected {
  background-color: #CFD8DC !important;
  color: white;
}
.heroes {
  margin: 0 0 2em 0;
  list-style-type: none;
  padding: 0;
  width: 15em;
}
.heroes li {
  cursor: pointer;
  position: relative;
  left: 0;
  background-color: #EEE;
  margin: .5em;
  padding: .3em 0;
  height: 1.6em;
  border-radius: 4px;
}
.heroes li.selected:hover {
  background-color: #BBD8DC !important;
  color: white;
}
.heroes li:hover {
  color: #607D8B;
  background-color: #DDD;
  left: .1em;
}
.heroes .text {
  position: relative;
  top: -3px;
}
.heroes .badge {
  display: inline-block;
  font-size: small;
  color: white;
  padding: 0.8em 0.7em 0 0.7em;
  background-color:#405061;
  line-height: 1em;
  position: relative;
  left: -1px;
  top: -4px;
  height: 1.8em;
  margin-right: .8em;
  border-radius: 4px 0 0 4px;
}
</style>
