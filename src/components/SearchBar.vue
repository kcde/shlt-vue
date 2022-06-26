<script>
   export default {
      data() {
         return {
            location: null,
            minAmount: "",
            maxAmount: "",
            numberOfRooms: null,
            tradeType: "rent",
            propertyType: null,
            wfh: true,
         };
      },
      methods: {
         log() {
            console.log(this.location);
         },
      },
   };
</script>
<template>
   <form class="form">
      <div class="input-container">
         <select id="location" v-model="location" name="location" @change="log">
            <option :value="null">Desired Location</option>
            <option>Dabhin</option>
            <option>what</option>
            <option>no</option>
         </select>
      </div>
      <div class="input-container hide-input">
         <input v-model="minAmount" type="number" />
      </div>
      <div class="input-container hide-input">
         <input v-model="maxAmount" type="number" />
      </div>
      <div class="input-container">
         <select
            id="bedrooms"
            v-model="numberOfRooms"
            name="bedrooms"
            @change="log">
            <option :value="null">Bedrooms</option>
            <option>1</option>
            <option>2</option>
            <option>3</option>
            <option>4</option>
            <option>5+</option>
         </select>
      </div>
      <div class="input-container hide-input">
         <select
            id="tradeType"
            v-model="tradeType"
            name="tradeType"
            @change="log">
            <option>rent</option>
            <option>buy</option>
            <option>sale</option>
         </select>
      </div>
      <div class="input-container hide-input">
         <select
            id="location"
            v-model="propertyType"
            name="location"
            @change="log">
            <option :value="null">Property type</option>
            <option>Single</option>
            <option>Apartment</option>
            <option>no</option>
         </select>
      </div>

      <div class="input-container wfh hide-input">
         <input id="wfh" name="wfh" type="checkbox" v-model="wfh" />

         <label for="wfh"> WFH </label>
      </div>

      <button class="search-btn">SEARCH</button>
   </form>
</template>
<style>
   .input-container {
      background-color: var(--clr-white);
      border: 1px solid lightgray;
      padding: 1rem 1rem;
   }

   input,
   select {
      border: none;
      background-color: transparent;
      width: 100%;
      outline: none;
   }

   .wfh input {
      width: auto;
   }

   .hide-input {
      display: none;
   }
   .search-btn {
      background-color: var(--clr-blue);
      color: var(--clr-white);
      padding: 0.6rem 2rem;
      font-size: 1rem;

      display: block;
      margin: 1rem auto 0 auto;
   }

   .form > * + * {
      margin-top: 1.5rem;
   }

   @media screen and (min-width: 598px) {
      .form {
         display: grid;
         grid-template-columns: repeat(2, 1fr);
         grid-column-gap: 2rem;
         grid-row-gap: 1.5rem;
      }
      .form > * + * {
         margin-top: 0;
      }

      .hide-input {
         display: initial;
      }

      .search-btn {
         margin: 0;
      }
   }

   @media screen and (min-width: 1024px) {
      .form {
         grid-template-columns: repeat(4, 1fr);
      }
   }
</style>
