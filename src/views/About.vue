<template>
  <div class="about">
    <transition
      appear
      @before-enter="beforeEnter"
      @enter="enter"
      @after-enter="afterEnter"
    >
      <h1>About</h1>
    </transition>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam
      officia possimus delectus inventore quod quisquam culpa voluptas iusto,
      quae maiores quo dolorum, corporis laboriosam a dolore consequatur
      assumenda nam!
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam
      officia possimus delectus inventore quod quisquam culpa voluptas iusto,
      quae maiores quo dolorum, corporis laboriosam a dolore consequatur
      assumenda nam!
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam
      officia possimus delectus inventore quod quisquam culpa voluptas iusto,
      quae maiores quo dolorum, corporis laboriosam a dolore consequatur
      assumenda nam!
    </p>
  </div>
</template>

<script>
import gsap from "gsap";
import { ref } from "@vue/reactivity";
export default {
  setup() {
    const beforeEnter = (el) => {
      console.log("befE");
      el.style.transform = "translateY(-60px)";
      el.style.opacity = 0;
    };
    const enter = (el, done) => {
      console.log("ent");
      gsap.to(el, {
        y: 0,
        opacity: 1,
        duration: 2,
        ease: "bounce",
        onComplete: done,
      });
    };
    const afterEnter = () => {
      console.log("afterE");
    };
    // const afterEnter = (el) => {
    //   console.log("aftE");
    //   el.style.color = "green";

    //   setTimeout(() => {
    //     (showTitle.value = false), 2000;
    //   });
    // };
    // const beforeLeave = (el) => {
    //   el.style.color = "red";
    //   console.log("befL");
    // };
    // const leave = () => {
    //   console.log("lea");
    // };
    // const afterLeave = () => {
    //   console.log("aftL");
    // };
    return {
      beforeEnter,
      enter,
      afterEnter,
    };
  },
};
</script>

<style>
.about {
  max-width: 600px;
  margin: 20px auto;
}
</style>
