<script setup>
import { headerNav } from "@/constants/index";
</script>

<template>
  <header id="header" role="banner">
    <div class="header__inner">
      <div class="header__logo">
        <h1>
          <a href="#">PORTFOLIO<em>VUE.JS</em></a>
        </h1>
      </div>
      <nav class="header__nav" :class="{ show: isNavVisible }" role="navigation" aria-label="메인 메뉴">
        <ul>
          <li v-for="(nav, key) in headerNav" :key="key"><a href="nav.url">{{ nav.title }}</a></li>
        </ul>
      </nav>
      <div 
        class="header__nav__mobile" 
        id="headerToggle" 
        aria-controls="primary-menu" 
        :aria-expanded="isNavVisible.toString()" 
        role="button" 
        tabindex="0"
        @click="toggleMobileMenu"
      >
        <span></span>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      isNavVisible: false
    }
  },
  methods: {
    toggleMobileMenu() {
      this.isNavVisible = !this.isNavVisible;
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin";

#header {
  @include position-fixed;
  z-index: 10000;
}

.header__inner {
  @include flex-between;
  background-color: rgba(116, 99, 99, 0.1);
  backdrop-filter: blur(15px);
  padding: 1rem;

  .header__logo {
    font-size: 0.9rem;
    text-align: center;
    line-height: 1;

    em {
      font-size: 10px;
      display: block;
      color: var(--black200);
    }
  }

  .header__nav {

    @media (max-width: 768px){
      display: none;

      &.show {
        display: block;

        ul {
          display: block;
          position: absolute;
          right: 0;
          top: 68px;
          background-color: rgba(116,99,99,0.1);
          backdrop-filter: blur(15px);
          z-index: 10000;
          min-width: 150px;
          padding: 20px 0;

          li {
            display: block;
            text-align: right;

            a {
              display: inline-block;
              padding: 10px;
            }
          }
        }
      }

      &.show + .header__nav__mobile span::before {
        width: 20px;
      }

      &.show + .header__nav__mobile span::after {
        width: 20px;
      }
    }
    
    li {
      display: inline;

      a {
        font-size: 14px;
        padding: 14px;
        position: relative;

        &::before {
          content: '';
          width: calc(100% - 28px);
          height: 1px;
          background-color: var(--black);
          position: absolute;
          left: 14px;
          bottom: 10px;
          transform: scaleX(0);
          transition: all 0.3s;
        }

        &:hover::before {
          transform: scaleX(1);
        }
      }
    }
  }
  
  .header__nav__mobile {
    display: none;
    width: 40px;
    height: 40px;
    cursor: pointer;

    @media (max-width: 768px){
      display: block;
    }

    span {
      display: block;
      width: 40px;
      height: 2px;
      background-color: var(--black);
      margin-top: 19px;
      position: relative;

      &::before {
        content: "";
        width: 40px;
        height: 2px;
        background-color: var(--black);
        position: absolute;
        right: 0;
        top: 6px;
        transition: width 0.3s;
      }

      &::after {
        content: "";
        width: 40px;
        height: 2px;
        background-color: var(--black);
        position: absolute;
        left: 0;
        bottom: 6px;
        transition: width 0.3s;
      }
    }
  }
} 
</style>