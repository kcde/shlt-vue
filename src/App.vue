<script>
   import Header from "./components/Header.vue";
   import SearchBar from "./components/SearchBar.vue";
   import PropertyCard from "./components/PropertyCard.vue";
   import Footer from "./components/Footer.vue";

   // This starter template is using Vue 3 <script setup> SFCs
   // Check out https://vuejs.org/api/sfc-script-setup.html#script-setup

   export default {
      components: {
         Header,
         SearchBar,
         PropertyCard,
         Footer,
      },
      data() {
         return {
            name: [1],
            location: "",
            properties: "",
         };
      },

      async mounted() {
         const res = await fetch(
            "http://abellatsl.com/shelterbackend/public/api/fetchpropertiesrandomly"
         );
         const data = await res.json();
         console.log(data);
         this.properties = data.properties;
         console.log(this.properties);
      },
   };
</script>

<template>
   <Header v-if="true" />

   <section class="hero">
      <div class="hero__container">
         <div class="hero__text">
            <h1>Do More With <span>Shelta.</span></h1>
            <p>Rent, Lease or Buy Properties</p>
         </div>

         <SearchBar />
      </div>
   </section>
   <vue-loaders-ball-beat color="red" scale="1"></vue-loaders-ball-beat>
   <section class="property">
      <h2>
         Best property offers and deals
         <span class="text-blue">around you...</span>
      </h2>

      <div class="property__list" v-if="properties">
         <PropertyCard
            v-for="property in properties"
            :key="property.id"
            :property="property" />
      </div>
      <div class="spinning-dots" v-else></div>
   </section>

   <Footer />
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

   .hero {
      background-image: url("./assets/building.svg");
      width: 100%;
      position: relative;
      background-position: top center;
      background-repeat: no-repeat;
      background-blend-mode: lighten;
      color: black;
      z-index: 0;
      padding: 8rem 2rem 1rem 2rem;
      margin-bottom: 2rem;
   }

   .hero__container {
      max-width: 1024px;
      margin: 0 auto;
   }

   .hero__text {
      text-align: center;
      margin-bottom: 1rem;
   }

   .hero__text span {
      color: var(--clr-blue);
   }

   .hero__text h1 {
      font-size: 40px;
      font-weight: 500;
   }

   .hero__text p {
      font-weight: 700;
      font-size: 1rem;
   }

   .hero::before {
      content: "";
      position: absolute;
      z-index: -1;
      background-color: hsla(0, 0%, 100%, 0.9);
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
   }

   .text-blue {
      color: var(--clr-blue);
   }

   .property__list {
      padding: 0 1rem;
      display: flex;
      flex-direction: column;
      gap: 2rem;
   }

   .property h2 {
      text-align: center;
      font-weight: 300;
      font-size: 1.5rem;
      margin-bottom: 2rem;
   }

   @-webkit-keyframes spin {
      to {
         -webkit-transform: rotate(360deg);
         transform: rotate(360deg);
      }
   }

   @keyframes spin {
      to {
         -webkit-transform: rotate(360deg);
         transform: rotate(360deg), scale(2);
      }
   }

   .spinning-dots {
      margin: 10rem auto 0 auto;
      -webkit-animation: spin 1.5s infinite linear;
      animation: spin 1.5s infinite linear;
      border-radius: 10px;
      -webkit-box-shadow: 25px 0px 0 0 var(--blue),
         15.58725px 19.54579px 0 0 var(--clr-blue),
         -5.56302px 24.3732px 0 0 var(--clr-blue),
         -22.52422px 10.84709px 0 0 var(--clr-blue),
         -22.52422px -10.84709px 0 0 var(--clr-blue),
         -5.56302px -24.3732px 0 0 var(--clr-blue),
         15.58725px -19.54579px 0 0 var(--clr-blue);
      box-shadow: 25px 0px 0 0 var(--clr-blue),
         15.58725px 19.54579px 0 0 var(--clr-blue),
         -5.56302px 24.3732px 0 0 var(--clr-blue),
         -22.52422px 10.84709px 0 0 var(--clr-blue),
         -22.52422px -10.84709px 0 0 var(--clr-blue),
         -5.56302px -24.3732px 0 0 var(--clr-blue),
         15.58725px -19.54579px 0 0 var(--clr-blue);
      top: 0;
      height: 10px;
      width: 10px;
   }

   @media screen and (min-width: 768px) {
      .hero {
         padding: 12rem 2rem 1rem 2rem;
      }
      .hero__text h1 {
         font-size: 70px;
      }

      .hero__text p {
         font-size: 1.5rem;
      }

      .property__list {
         display: grid;
         grid-template-columns: repeat(auto-fill, minmax(400px, 1fr));
      }
   }
</style>
