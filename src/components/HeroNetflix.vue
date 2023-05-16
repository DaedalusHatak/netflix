<script setup lang="ts">
import { ref } from 'vue';

const isActive = ref<boolean>()
const emailData = ref<string>('')
</script>

<template>
        <img
      class="hero-img"
      src="@/assets/hero.jpg"
      alt=""
    />
    <div class="shadow-hero-image"></div>
    <div class="hero-wrapper">
      <nav>
        <span class="logo-span"
          ><img src="@/assets/daedalus.png" alt="">
        </span>
        <button class="sign-in-button">Sign In</button>
      </nav>
      <div class="flex-hero">
        <div class="info">  <h1>THIS IS NOT NETFLIX PAGE</h1>
          <h1>IT IS ONLY PORTFOLIO PURPOSE</h1>
          <h3>DON'T USE YOUR ACTUAL NETFLIX DATA</h3>
        </div>
        <div class="header-hero">
       
          <h1>Unlimited movies, TV shows, and more</h1>
      
          <p class="subtitle-hero">Watch anywhere. Cancel anytime.</p>
          <div class="get-started">
            <h3>Ready to watch? Enter your email to create or restart your membership.</h3>
            <form action="">
              <div class="input">
                <label :class="isActive ? 'label-active' : 'label'" for="emailfield"
                  >Email address</label
                >
                <input
                  v-model="emailData"
                  @focusout="emailData === '' ? (isActive = false) : (isActive = true)"
                  @focusin="isActive = true"
                  type="text"
                  autocomplete="email"
                  id="emailfield"
                  minlength="5"
                  maxlength="50"
                />
              </div>
              <button class="get-started-button">
                Get Started
                <svg
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                  class="Hawkins-Icon Hawkins-Icon-Standard"
                  data-name="ChevronRight"
                >
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7.29297 19.2928L14.5859 12L7.29297 4.70706L8.70718 3.29285L16.7072 11.2928C16.8947 11.4804 17.0001 11.7347 17.0001 12C17.0001 12.2652 16.8947 12.5195 16.7072 12.7071L8.70718 20.7071L7.29297 19.2928Z"
                    fill="currentColor"
                  ></path>
                </svg>
              </button>
            </form>
          </div>
        </div>
      </div>
    </div>
</template>
<style scoped lang="scss">
@media screen and (min-width: 600px) {
  nav {
    max-width: calc(100% - 4rem);
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
.info{
  color:gold;

inset: 0;
margin: auto;
text-align: center;
 h1{
  font-size:2.5rem;
  font-family:fantasy;
  letter-spacing: 0.2ch;
  text-decoration:underline;
  font-weight: 600;
 }
 h3{
  font-size: 2rem;
  padding-top: 1rem;
  font-weight: 600;
 }
}
@media (min-width: 720px) {

  .info{
    position: absolute;
    inset: 0;
    top: 70px;
    h1{
  font-size:2.8rem;
  font-family:fantasy;
  letter-spacing: 0.2ch;
  text-decoration:underline;
  font-weight: 600;
 }
 h3{
  font-size: 2rem;
  font-weight: 600;
 }
  }
  
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
  height: 100%;
  width: 100%;
  
  position: absolute;
  object-fit: cover;
  transform: scale(1.25) translateY(-10%);
  overflow: hidden;
}
.flex-hero {
  display: flex;
  flex-direction: column;
  padding: 9.875rem 0 4rem;
  min-height: 43.75rem;
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
.header-hero {
  max-width: calc(100% - 4rem);
  margin: auto;
  color: white;
  text-align: center;
  font-size: 50px;
}
.subtitle-hero {
  margin: 1rem 0 0;
}
.get-started {
  margin: 1.5rem 0 0;
}

.logo {
  width: 9.25rem;
  height: 2.5rem;
  color: rgba(229, 9, 20, 1);
  fill: currentColor;
  display: block;
}

.input {
  display: flex;
  flex: 1 1 auto;
  border: 1px solid;
  border-radius: 0.25rem;
  background: rgba(22, 22, 22, 0.7);
  border-color: rgba(128, 128, 128, 0.7);
  font-size: 1rem;
  font-weight: 400;
  min-width: 12.5rem;

  height: 3.5rem;
  padding: 0px;

  color: rgb(255, 255, 255);
}
input {
  color: white;
  padding: 1.5rem 1rem 0.5rem;
  border: none;
  min-height: 16px;
  min-width: 16px;
  width: 100%;
  background-clip: padding-box;
  appearance: none;
  background: transparent;
}

.label {
  position: absolute;
  z-index: 1;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  transition-property: top, font-size, line-height;
  transition-duration: 250ms;
  pointer-events: none;
  font-size: 1rem;
  transition-timing-function: cubic-bezier(0.9, 0, 0.51, 1);
  color: rgba(255, 255, 255, 0.7);
  left: 1rem;
  line-height: 1.5rem;
  right: 1rem;
  top: 1rem;
}

.label-active {
  position: absolute;
  z-index: 1;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  transition-property: top, font-size, line-height;
  transition-duration: 250ms;
  pointer-events: none;
  font-size: 0.75rem;
  transition-timing-function: cubic-bezier(0.5, 0, 0.1, 1);
  color: rgba(255, 255, 255, 0.7);
  left: 1rem;
  line-height: 1.125rem;
  right: 1rem;
  top: 0.5rem;
}

.sign-in-button {
  z-index: 1000;
  border: 0;
  border-radius: 0.25rem;
  cursor: pointer;
  fill: currentColor;
  position: relative;
  transition-duration: 250ms;
  transition-property: background-color, border-color;
  transition-timing-function: cubic-bezier(0.9, 0, 0.51, 1);
  vertical-align: text-top;
  width: auto;
  line-height: 1;
  font-size: 0.875rem;
  font-weight: 500;
  min-height: 2rem;
  padding: 0.25rem 0.95rem;
  background: rgb(229, 9, 20);
  color: rgb(255, 255, 255);
}
.get-started-button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  writing-mode: horizontal-tb !important;
  width: max-content;
  border: 0px;
  margin-left: 0.5rem;
  font-size: 1.5rem;
  font-weight: 600;
  min-height: 3.5rem;
  padding: 0.75rem 1.5rem;
  background: rgb(229, 9, 20);
  color: rgb(255, 255, 255);
  border-radius: 0.25rem;
}
form {
  max-width: 36.625rem;
  align-items: flex-start;
  text-align: left;
  margin: 1rem auto 0;
  vertical-align: text-top;
  display: flex;
  width: 100%;
  max-width: 36.625rem;
}
</style>