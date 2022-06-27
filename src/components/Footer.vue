<script>
   import abellaLogo from "../assets/abella-logo.svg";
   export default {
      data() {
         return {
            abellaLogoUrl: abellaLogo,
         };
      },
   };
</script>

<template>
   <footer>
      <div class="footer-main">
         <div class="footer-intro">
            <h4 class="text-blue">Sign up to our newsletters</h4>
            <p>
               Be one of the first to know about product launches, promotions
               and more.
            </p>
            <div class="footer-input">
               <input type="email" placeholder="Enter your email" />
               <button>
                  <i class="fa-solid fa-arrow-right-long"></i>
               </button>
            </div>
         </div>

         <div class="footer-about">
            <div>
               <h6>COMPANY</h6>
               <p>Blog</p>
               <p>About us</p>
               <p>Tenant</p>
               <p>Landlord</p>
               <p>Careers</p>
               <p>Property management</p>
            </div>

            <div>
               <h6>Support</h6>
               <p>Help & FAQ</p>
               <p>hello@myshelta.com</p>
               <p>sheltaoffice@gmail.com</p>
               <p>(+234) 0806 179 6909</p>
            </div>
         </div>
      </div>

      <div class="footer-copy">
         <div class="copyright">
            &copy;{{ new Date().getFullYear() }} <span>a product of </span>
            <div class="abella-logo">
               <img :src="abellaLogoUrl" alt="abella logo" />
            </div>
         </div>

         <div class="footer-icons">
            <button class="social-icon">
               <i class="fa-brands fa-facebook-f"></i>
            </button>
            <button class="social-icon">
               <i class="fa-brands fa-instagram"></i>
            </button>
            <button class="social-icon">
               <i class="fa-brands fa-twitter"></i>
            </button>
            <button class="social-icon">
               <i class="fa-brands fa-linkedin"></i>
            </button>
         </div>
      </div>
   </footer>
</template>

<style>
   footer {
      margin-top: 5rem;
   }

   .footer-main {
      padding: 0 1rem;
   }

   footer h4 {
      font-size: 1.5rem;
      font-weight: 500;
      margin-bottom: 8px;
   }

   footer h6 {
      font-size: 18px;
   }

   .footer-input {
      display: flex;
      border-bottom: 1px solid lightgray;
      padding: 10px 1rem;
      margin-bottom: 3rem;
      margin-top: 1rem;
   }
   .footer-input button {
      background-color: var(--clr-yellow);
      width: 100px;
      border-radius: 0;
   }

   .footer-about > * + * {
      margin-top: 2.5rem;
   }

   .footer-about div > * + * {
      margin-top: 1rem;
   }

   .footer-copy {
      background-color: var(--clr-blue);
      color: var(--clr-white);
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 1rem;
      margin-top: 4rem;
   }
   .copyright {
      font-size: 12px;
   }

   .abella-logo {
      max-width: 40px;
      display: inline-block;
   }

   .social-icon {
      background-color: transparent;
      color: var(--clr-white);
      font-size: 1rem;
      margin-right: 1rem;
      padding: 5px;
   }

   @media screen and (min-width: 768px) {
      .footer-main {
         display: flex;
         /* gap: 2.5rem; */
         align-items: center;
         justify-content: space-between;
      }

      .footer-intro {
         flex: 1;
      }

      .footer-about {
         display: flex;
         justify-content: space-around;
         flex: 1;
      }
      .footer-about > * + * {
         margin-top: 0;
      }
   }
</style>
