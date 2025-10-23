<script setup lang="ts">
import { onMounted, ref } from 'vue';
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import gsap from 'gsap'
import { CSSPlugin } from 'gsap/CSSPlugin';
const container = ref(null);
const content = ref(null);

const title = ref(null);
const paraOne = ref(null);
const paraTwo = ref(null);
const paraThree = ref(null);

  /*gsap.fr  om(container.value, {*/
onMounted(() => {
  gsap.from(container.value.children, {
    delay: 0.5,
    duration: 1,
    y: '+100',
    autoAlpha: 0,
    stagger: 0.25,
    ease: "back.out(1.7)",
  })

  console.log(paraTwo.value);

  const tl =gsap.timeline({ delay:1, paused: true});
  tl.from(title.value, { x: '-200', autoAlpha: 0, duration: 1});
  tl.from(paraOne.value, { x: '+200', autoAlpha: 0, duration: 1});
  tl.from(paraTwo.value, { x: '-200', autoAlpha: 0, duration: 1});
  tl.from(paraThree.value, { x: '+200', autoAlpha: 0, duration: 1}); 
  tl.play();
})
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div ref="container" class="wrapper">
      <HelloWorld msg="You did it!" />
      <div ref="content">
        <H1 ref="title">Headline Goes Here Test</H1>
        <p ref="paraOne">Lorem ipsum dolor sit amet consectetur adipisicing elit. Eveniet, ab ex dolor aliquid iure quidem cum sunt possimus natus dolores eius officia reiciendis autem fugiat, voluptate perferendis a quas quasi. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quos quae ad ut facilis excepturi dolorum distinctio magnam quibusdam laborum sequi similique, consequatur sapiente ratione explicabo ipsam libero? Aliquid, similique autem! Lorem ipsum, dolor sit amet consectetur adipisicing elit.  </p>
        <p ref="paraTwo">Lorem ipsum dolor sit amet consectetur adipisicing elit. Eveniet, ab ex dolor aliquid iure quidem cum sunt possimus natus dolores eius officia reiciendis autem fugiat, voluptate perferendis a quas quasi. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quos quae ad ut facilis excepturi dolorum distinctio magnam quibusdam laborum sequi similique, consequatur sapiente ratione explicabo ipsam libero?  </p>
        <p ref="paraThree">Lorem ipsum dolor sit amet consectetur adipisicing elit. Eveniet, ab ex dolor aliquid iure quidem cum sunt possimus natus dolores eius officia reiciendis autem fugiat, voluptate perferendis a quas quasi. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quos quae ad ut facilis excepturi dolorum distinctio magnam quibusdam laborum  alias!</p>
      
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
