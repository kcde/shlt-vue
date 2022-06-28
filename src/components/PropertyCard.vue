<script>
   export default {
      props: ["property"],
      mounted() {},
      computed: {
         price() {
            return Number(this.property.price).toLocaleString();
         },
      },
   };
</script>

<template>
   <div class="property__card" v-if="property">
      <div class="property-tag">Rent</div>
      <div class="property-img">
         <img :src="property.oneimageurl" alt=" property image" />
      </div>
      <div class="property-info">
         <div class="info">
            <p class="property-name">
               {{ property.title }}
            </p>
            <p class="property-address">
               <i class="fa-solid fa-location-dot"></i> {{ property.city }},
               {{ property.state }}
            </p>
            <p class="property-desc">{{ property.description }}</p>
         </div>
         <p class="property-price">
            ₦ {{ price }}
            <span>per annum</span>
         </p>
         <div class="property-details">
            <div>
               <i class="fa-solid fa-bed"></i>
               <p>{{ property.bedrooms }} Bedrooms</p>
            </div>
            <div>
               <i class="fa-solid fa-bath"></i>
               <p>{{ property.bathrooms }} Bathrooms</p>
            </div>
            <div>
               <i class="fa-solid fa-toilet"></i>
               <p>{{ property.toilets }} toilet</p>
            </div>
            <div>
               <i class="fa-solid fa-square-parking"></i>
               <p>{{ property.parking }} parking</p>
            </div>
         </div>
      </div>
   </div>
</template>

<style>
   .info > * + * {
      margin-top: 0.5rem;
   }

   .property__card {
      position: relative;
   }

   .property-img {
      height: 300px;
   }
   .property-img img {
      height: 100%;
      object-fit: cover;
   }

   .property-info {
      padding: 1.5rem;
      background-color: var(--clr-white);
      border-radius: 6px 25px;
      border: 1px solid lightgray;
      margin-left: 1rem;
      margin-right: 1rem;
      margin-top: -2.5rem;
      position: relative;
      z-index: 2;
   }

   .property-name {
      font-size: 1.3rem;
      overflow: hidden;
      text-overflow: ellipsis;
      white-space: nowrap;
      font-weight: 500;
   }
   .property-address {
      color: gray;
   }
   .property-desc {
      font-size: 12px;
   }
   .property-price {
      font-size: 1.5rem;
      font-weight: 600;
      margin-top: 1rem;
   }

   .property-price span {
      font-size: 14px;
   }

   .property-details {
      display: flex;
      justify-content: space-between;
      margin-top: 1rem;
   }
   .property-details > div {
      text-align: center;
   }
   .property-details p {
      font-size: 10px;
      font-weight: 600;
   }

   .property-tag {
      background-color: var(--clr-blue);
      background: linear-gradient(180deg, #6886f0, #0033ea 99.48%);
      color: var(--clr-white);
      position: absolute;
      font-size: 14px;
      top: -10px;
      left: 50%;
      transform: translateX(-50%);
      width: 100px;
      padding: 2px 0;
      text-align: center;
   }

   @media screen and (min-width: 489px) {
      .property-details p {
         font-size: 1rem;
      }
   }
</style>
