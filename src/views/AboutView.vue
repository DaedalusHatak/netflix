<script setup lang="ts">
import BaseInput from '@/components/BaseInput.vue';


</script>

<template>
  <img class="hero-img" src="@/assets/hero.jpg" alt="" />
  <div class="shadow-hero-image"></div>
  <div class="hero-wrapper">
    <nav>
      <span class="logo-span"><img src="@/assets/daedalus.png" alt="" /> </span>
    </nav>
    <div class="flex-hero">

      <div class="form-hero">
        <h1>Sign In</h1>
        <form name="login">
         <div>
          <BaseInput name="Email or phone number" type="email" :background="true"/>
         </div>
         <div>
          <BaseInput name="Password" type="password"  :background="true"/>
         </div>
         <button class="get-started-button">
                Sign In
              </button>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
h1{
  text-align: left;
  margin-bottom: 50px;
}

nav {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  height: 5.375rem;
  margin: auto;
  width: 100%;
  position: absolute;
  left: 0;
  right: 0;
}
.logo-span {
  margin-right: auto;
}
.hero-image {
  background: rgb(0 0 0 / 40%);
}
.hero-wrapper {
  margin: auto;
}
.hero-img {
  display: none;
}
.flex-hero {


  padding: 9.875rem 0 4rem;
  min-height: 43.75rem;
}
a {
  display: flex;
  align-items: center;
  text-decoration: none;
}
.shadow-hero-image {
  background: rgb(0 0 0 / 40%);
  background-image: linear-gradient(
    to top,
    rgba(0, 0, 0, 0.8) 0,
    rgba(0, 0, 0, 0) 60%,
    rgba(0, 0, 0, 0.8) 100%
  );
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
}
.form-hero {

  
padding: 4rem 1rem;
  margin: 0 auto;
  color: white;
  text-align: center;
  font-size: 50px;
 
}
form{
  display: flex;
  gap: 20px;

  flex-direction: column;
  justify-content: center;
  text-align: left;
  position: relative;

}
.subtitle-hero {
  margin: 1rem 0 0;
}

.logo {
  width: 9.25rem;
  height: 2.5rem;
  color: rgba(229, 9, 20, 1);
  fill: currentColor;
  display: block;
}
.get-started-button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  writing-mode: horizontal-tb !important;
  width: 100%;
  margin-top:1rem;
  flex: 0 0 auto;
  border: 0px;
 
  font-size: 1.5rem;
  font-weight: 500;
  min-height: 3.5rem;
  padding: 0.75rem 1.5rem;
  background: rgb(51, 26, 187,0.9);
  cursor: pointer;
  color: rgb(255, 255, 255);
  border-radius: 1rem;
}


@media screen and (min-width: 600px) {
  nav {
    max-width: calc(100% - 4rem);
  }
  .hero-img {
  height: 100%;
  width: 100%;
display:block !important;
  position: absolute;
  object-fit: cover;
  transform: scale(1.25) translateY(-10%);
  overflow: hidden;
}
.flex-hero {

max-width: 450px;
margin: auto;
 padding: 9.875rem 0 4rem;
 min-height: 43.75rem;
}
  .form-hero {

  min-width: 500px;
  padding: 4rem 4rem;
  max-width: calc(100% - 4rem);
  margin: 0 auto;
  color: white;
  text-align: center;
  font-size: 50px;
  background-color: rgba($color: #000000, $alpha: 0.8);
}
}
@media screen and (min-width: 1280px) {
  nav {
    max-width: calc(83.33333333333334% - 6rem);
  }
}
@media screen and (min-width: 1920px) {
  nav {
    max-width: calc(66.66666666666666% - 6rem);
  }
}

@media (min-width: 720px) {
  .info {
    position: absolute;
    inset: 0;
    top: 70px;
    h1 {
      font-size: 2.8rem;
      font-family: fantasy;
      letter-spacing: 0.2ch;
      text-decoration: underline;
      font-weight: 600;
    }
    h3 {
      font-size: 2rem;
      font-weight: 600;
    }
  }
}
</style>
