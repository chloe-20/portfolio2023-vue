<script setup>
import { portText } from "@/constants/index";
</script>

<template>
  <section id="portfolio">
    <div class="portfolio__inner">
      <div class="portfolio__title">PORTFOLIO <em>포트폴리오 작업물(수정예정)</em></div>
      <div class="portfolio__wrap">
        <article class="portfolio__item" v-for="(port, key) in portText" :key="key">
          <span class="num">{{ port.num }}.</span>
          <a :href="port.code" target="_blank" class="img">
            <img :src="port.img" :alt="port.name" />
          </a>
          <h3 class="title">{{ port.title }}</h3>
          <p class="desc">{{ port.desc }}</p>
          <a :href="port.view" target="_blank" class="site">사이트 보기</a>
        </article>          
      </div>
    </div>
  </section>
</template>

<script>
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
  mounted: function () {
    this.scrollAnimation();
  },
  methods: {
    scrollAnimation() {
      const horSection = gsap.utils.toArray(".portfolio__item");

      gsap.to(horSection, {
        xPercent: -120 * (horSection.length - 1),
        ease: "none",
        scrollTrigger: {
          trigger: "#portfolio",
          start: "top 56px",
          end: "+=3000",
          pin: true,
          scrub: 1,
          markers: false,
          invalidateOnRefresh: true,
          anticipatePin: 1,
        },
      });
    },
  },
};
</script>

<style lang="scss">
#portfolio {
  width: 100%;
  margin-top: 30vh;
  overflow: hidden;
}
.portfolio__inner {
  padding: 16px;

  .portfolio__title {
    width: 100%;
    height: 5vw;
    font-size: 4vw;
    font-weight: 900;
    line-height: 1.6;
    font-family: var(--mainKor-font);
    color: var(--black100);
    border-bottom: 0.4vw solid var(--black100);
    margin-bottom: 16px;
    text-indent: -0.26vw;

    em {
      font-size: 1.25rem;
      font-weight: 400;
      line-height: 2;
    }
  }

  .portfolio__wrap {
    display: flex;
    flex-wrap: wrap;
    width: 7000px;

    .portfolio__item {
      width: 500px;
      height: 75vh;
      background-color: var(--subBg100);
      padding: 2.5rem;
      margin-right: 20px;

      &:nth-child(1) {
        background-color: var(--subBg100);
      }
      
      &:nth-child(2) {
        background-color: var(--subBg200);
      }
      
      &:nth-child(3) {
        background-color: var(--subBg300);
      }
      
      &:nth-child(4) {
        background-color: var(--subBg400);
      }
      
      &:nth-child(5) {
        background-color: var(--subBg500);
      }
      
      &:nth-child(6) {
        background-color: var(--subBg100);
      }
      
      &:nth-child(7) {
        background-color: var(--subBg200);
      }
      
      &:nth-child(8) {
        background-color: var(--subBg300);
      }
      
      &:nth-child(9) {
        background-color: var(--subBg400);
      }
      
      &:nth-child(10) {
        background-color: var(--subBg500);
      }

      .num {
        font-size: 2rem;
        font-family: var(--mainNum-font);
      }

      .img {
        display: block;
        margin-top: -20px;
        transition: margin-top 0.3s;

        img {
          border-radius: 5px;
          filter: saturate(0%);
          transition: all 0.3s;
        }
        
        &:hover {
          margin-top: 0;

          img {
            filter: saturate(100%);
          }
        }
      }

      .title {
        font-size: 1.5rem;
        text-align: center;
        padding: 0.8rem 0;
        font-weight: 700;
        color: var(--black100);
        border-bottom: 2px solid var(--black100);
        margin-bottom: 1rem;
      }

      .desc {
        font-size: 1rem;
      }

      .site {
        border: 1px solid var(--black100);
        display: block;
        text-align: center;
        padding: 0.625rem 1.5rem;
        margin-top: 1.5rem;
        transition: all 0.2s;

        &:hover {
          background-color: var(--black100);
          color: var(--white);
        }
      }
    }
  }
}
</style>