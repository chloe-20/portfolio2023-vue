<script setup>
import { RouterView } from "vue-router";
</script>

<template>
    <RouterView />
</template>

<script>
import Lenis from "@studio-freight/lenis";

export default {
    mounted: function () {
        this.scrollAnimation();
    },
    methods: {
        scrollAnimation() {
            const lenis = new Lenis({
                duration: 1,
                easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)),
                direction: "vertical",
                gestureDirection: "vertical",
                smooth: true,
            });

            function raf(time) {
                lenis.raf(time);
                requestAnimationFrame(raf);
            }

            requestAnimationFrame(raf);

            lenis.on("scroll", (e) => {
                console.log(e);
            });
        },
    },
};
</script>