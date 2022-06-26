<script>
   import Navbar from "./Navbar.vue";

   export default {
      components: { Navbar },
      data() {
         return {};
      },
   };
</script>

<template>
   <header>
      <div class="header__contact">
         <a href="mailto:hello@myshelta.com"
            ><i class="fa-solid fa-envelope"></i>hello@myshelta.com</a
         >

         <a
            href="https://api.whatsapp.com/send?phone=+2348061796909"
            target="_blank"
            rel="noopener noreferrer"
            ><i class="fa-brands fa-whatsapp"></i> (+234) 0806 179 6909</a
         >
      </div>

      <Navbar />
   </header>
</template>

<style>
   header {
      font-size: 12px;
      position: absolute;
      top: 0;
      width: 100%;
      z-index: 20;
   }

   .header__contact {
      display: flex;
      justify-content: space-between;
      background-color: var(--clr-blue);
      padding: 8px 15px;
      color: var(--clr-white);
   }

   .header__contact a:hover {
      opacity: 0.7;
   }

   .header__contact i {
      margin-right: 3px;
   }

   @media screen and (min-width: 768px) {
      header {
         font-size: 1rem;
      }
      .header__contact {
         padding: 8px 35px;
      }
   }
</style>
