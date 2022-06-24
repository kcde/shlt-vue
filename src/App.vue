<script>
   import Header from "./components/Header.vue";
   // This starter template is using Vue 3 <script setup> SFCs
   // Check out https://vuejs.org/api/sfc-script-setup.html#script-setup

   export default {
      components: { Header },
      data() {
         return {
            name: [1],
         };
      },
   };
</script>

<template>
   <Header />
   <p>
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quam fugit
      inventore voluptas libero, velit enim reprehenderit officiis recusandae
      tenetur culpa rerum eius maxime aliquid ducimus magni expedita deserunt
      deleniti similique?
   </p>
</template>

<style>
   :root {
      --clr-blue: #00f;
      --clr-yellow: #ffb100;
      --clr-white: #ffffff;
   }

   *,
   *::after,
   *::before {
      margin: 0;
      box-sizing: border-box;
   }

   img {
      width: 100%;
   }

   a {
      color: inherit;
      text-decoration: none;
   }

   #app {
      font-family: Avenir, Helvetica, Arial, sans-serif;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      color: #2c3e50;
   }

   button {
      display: inline-block;
      border-radius: 5px;

      padding: 10px 16px;
      border: none;
      cursor: pointer;
   }

   .btn-main {
      background-color: var(--clr-blue);
      color: var(--clr-white);
   }

   .btn-accent {
      background-color: var(--clr-yellow);
      color: var(--clr-white);
   }
</style>
