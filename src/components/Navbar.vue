<script>
   import sheltaLogo from "../assets/shelta.svg";

   export default {
      data() {
         return {
            logo: sheltaLogo,
            menuOpen: false,
            subMenuOpen: false,
         };
      },
      methods: {
         toggleMenu() {
            this.menuOpen = !this.menuOpen;
         },
         toggleSubMenu() {
            this.subMenuOpen = !this.subMenuOpen;
         },
      },
   };
</script>

<template>
   <nav>
      <div class="brand-logo">
         <img :src="logo" alt="shelta logo" />
      </div>

      <div class="nav__icon">
         <i class="fa-solid fa-bars" @click="toggleMenu"></i>
      </div>

      <div :class="{ 'menu-open': menuOpen }" class="links">
         <a href="#">Home</a>
         <a href="#">About us</a>
         <a href="#">Contact us</a>
         <a href="#">Rent payer</a>
         <a href="#">Blog</a>
         <a href="#">Buy</a>
         <a href="#">Properties</a>
         <div class="sub-list">
            <a href="#">How it works</a>
            <i
               class="fa-solid fa-caret-down"
               style="margin-left: 5px"
               @click="toggleSubMenu"></i>

            <div v-show="subMenuOpen">
               <a href="#">Tenant</a>
               <a href="#">Landlord</a>
               <a href="#">Facility Management</a>
            </div>
         </div>
         <a href="#">FAQs</a>
         <a href="#">Careers</a>
         <div class="nav__btn-container">
            <button class="btn btn-accent">Dashboard</button>
            <button class="btn btn-main">Login</button>
         </div>
      </div>
   </nav>
</template>

<style>
   nav {
      display: grid;
      grid-template-columns: 1fr 1fr;
      grid-template-areas:
         "logo nav-icon"
         "menu menu";
      transition: all 450ms ease-in;
      box-shadow: 0 10px 20px rgb(0 0 0 / 15%);
      overflow: hidden;
      padding: 0 1rem;
      background-color: var(--clr-white);
      position: absolute;
      width: 100%;
   }

   .brand-logo {
      width: 4rem;
      align-self: center;
      grid-area: logo;
   }

   .nav__icon {
      font-size: 2.5rem;
      color: var(--clr-blue);
      text-align: right;
      align-self: center;
      cursor: pointer;
      grid-area: nav-icon;
   }

   .links {
      grid-column: 1/3;
      display: flex;
      max-height: 0;
      flex-direction: column;
      text-align: center;
      background-color: --clr-white;
      font-size: 14px;
      font-weight: 500;
      transition: all 350ms ease-in-out;
      grid-area: menu;
   }

   .menu-open {
      max-height: 32rem;
      padding-bottom: 0px !important;
   }

   .nav__btn-container > * + * {
      margin: 0 0 1rem 1rem;
   }

   .links > * + * {
      margin-top: 1.5rem;
   }

   .sub-list {
      position: relative;
   }

   .sub-list > div {
      position: absolute;
      display: flex;
      flex-direction: column;
      min-width: 12rem;
      text-align: left;
      background-color: var(--clr-white);
      border: 1px solid lightgray;
      top: 2rem;
      border-radius: 5px;
      left: 50%;
      transform: translateX(-50%);
      /* z-index: 10; */
   }

   .sub-list > div > * {
      padding: 10px 1rem;
   }
   .sub-list > div > *:hover {
      background-color: lightgray;
   }

   @media screen and (min-width: 992px) {
      .brand-logo {
         width: 5rem;
      }

      nav {
         grid-template-areas: "logo  menu";
         grid-template-columns: auto 1fr;
         padding: 8px 1rem;
         overflow: visible;
      }

      .links {
         flex-direction: row;
         align-self: center;
         align-items: center;
         justify-content: flex-end;
         max-height: 32rem;
      }

      .links > * + * {
         margin-top: 0;
         margin-left: 1rem;
      }

      .nav__icon {
         display: none;
      }

      .nav__btn-container > * + * {
         margin: 0 0 0 1rem;
      }
   }
</style>
