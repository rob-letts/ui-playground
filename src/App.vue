<script setup lang="ts">
import { useTemplateRef } from 'vue'
import { useMotion } from '@vueuse/motion'
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'

const target = useTemplateRef('logo')

const motionInstance = useMotion(target, {
    initial: {
        opacity: 0,
        y: 100
    },
    enter: {
        opacity: 1,
        y: 0
    }
})

console.log(motionInstance)
</script>

<template>
  <header>
    <img
      ref="logo"
      alt="Vue logo"
      class="logo"
      src="@/assets/logo.svg"
      width="125"
      height="125"
    />

    <HelloWorld msg="Hi Rob" />
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </nav>
  </header>

  <RouterView />
</template>