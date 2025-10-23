<script setup lang="ts">
import { onMounted, ref } from 'vue';
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import gsap from 'gsap'

const container = ref(null);
const content = ref(null);

onMounted(() => {
  gsap.from(container.value, {
    delay: 0.5,
    duration: 1,
    y: '+100',
    autoAlpha: 0,
    ease: "back.out(1.7)",
  })
})
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div ref="container" class="wrapper">
      <HelloWorld msg="You did it!" />
      <div ref="content">
        <H1>Headline Goes Here</H1>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Eveniet, ab ex dolor aliquid iure quidem cum sunt possimus natus dolores eius officia reiciendis autem fugiat, voluptate perferendis a quas quasi. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quos quae ad ut facilis excepturi dolorum distinctio magnam quibusdam laborum sequi similique, consequatur sapiente ratione explicabo ipsam libero? Aliquid, similique autem! Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quos labore repellat quidem inventore natus eveniet iusto mollitia tenetur est sit dolorem, saepe reiciendis molestias itaque quas voluptate autem tempore alias!</p>
      </div>
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
