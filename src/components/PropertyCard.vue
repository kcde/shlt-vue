<script></script>

<template>
   <div class="property__card">
      <div class="property-img">
         <img
            src="https://myshelta.com/shelterbackend/public/storage/properties/adminpshelta957861643969472.jpg"
            alt=" property image" />
      </div>
      <div class="property-info">
         <div class="info">
            <p class="property-name">
               Fully furnished and serviced 4 bedroom Masionette Duplex, at
               Brains and Hammers Estate, Galadimawa
            </p>
            <p class="property-address">
               <i class="fa-solid fa-location-dot"></i> Lugbe Federal capital
            </p>
            <p class="property-desc">A block of 2 units of Self-contain</p>
         </div>
         <p class="property-price">₦ 250,000 <span>per annum</span></p>
         <div class="property-details">
            <div>
               <i class="fa-solid fa-bed"></i>
               <p>3 Bedrooms</p>
            </div>
            <div>
               <i class="fa-solid fa-bath"></i>
               <p>3 Bathrooms</p>
            </div>
            <div>
               <i class="fa-solid fa-toilet"></i>
               <p>4 toilet</p>
            </div>
            <div>
               <i class="fa-solid fa-square-parking"></i>
               <p>2 parking</p>
            </div>
         </div>
      </div>
   </div>
</template>

<style>
   .info > * + * {
      margin-top: 0.5rem;
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

   @media screen and (min-width: 489px) {
      .property-details p {
         font-size: 1rem;
      }
   }
</style>
