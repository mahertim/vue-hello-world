<template>
  <div class="heroDetail">
    <h2>{{ hero.name }}</h2>
    <div><span>id: {{ hero.id }}</span></div>
    <div>
      <label>name:
        <input v-model="hero.name" placeholder="hero.name" />
      </label>
    </div>
  </div>
</template>


<script>
import { Hero } from '../hero'

export default {
  name: 'HeroDetail',
  props: {
    hero: Hero
  }
}
</script>

<style>

</style>
