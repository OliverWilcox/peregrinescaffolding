<template>
  <div class="section2">
    <div class="aboutintoviewtrigger" ref="abt"></div>
    <h1 class="about">
      Local family run business with <br />over 40 years of experience in <br />
      all areas of scaffolding. We <br />
      specialise in domestic jobs, <br />and always work hard to <br />ensure
      great quality and a <br />friendly, no-fuss service.
    </h1>
    <div class="abouttrigger"></div>
    <div class="aboutline" ref="abtline"></div>
    <div class="reviewcontainer" v-bind:class="{ open }">
      <div class="reviewblock" ref="reviews">
        <h3 class="name1">Sean Lee Falcon</h3>
        <h1 class="review1">
          "Really great service, so quiet<br />
          that there's never an issue<br />
          having work done early or<br />
          when you need a lie in!"
        </h1>
        <h3 class="name2">CPS Decorating</h3>
        <h1 class="review2">
          "Friendly and hardworking guys. <br />
          Never any mess or issues, and <br />
          the jobs are always to a<br />
          high standard. I would <br />
          recommend them to anyone"
        </h1>
        <h3 class="name3">Paul, Apex Windows</h3>
        <h1 class="review3">
          Thank you for the friendly and <br />
          great service. I never had to <br />
          worry when leaving them keys <br />to the property when empty<br />.
          They always keep the area <br />tidy with no disruption. <br />
          I'd go with them again.
        </h1>
      </div>
    </div>
    <div class="slidercount" v-bind:class="{ open }">
      <div
        class="arrowright1"
        v-on:click="slide2On"
        v-bind:class="{ arrowright1off: isSlider2On }"
      >
        <i class="fas fa-chevron-right"></i>
      </div>
      <div
        class="arrowleft1"
        v-on:click="slide3On"
        v-bind:class="{ arrowleft1off: isSlider2On }"
      >
        <i class="fas fa-chevron-left"></i>
      </div>
      <div
        class="arrowright2"
        v-on:click="slide3On"
        v-bind:class="{ arrowright2on: isSlider2On }"
      >
        <i class="fas fa-chevron-right"></i>
      </div>
      <div
        class="arrowleft2"
        v-on:click="slide1On"
        v-bind:class="{ arrowleft2on: isSlider2On }"
      >
        <i class="fas fa-chevron-left"></i>
      </div>
      <div
        class="arrowright3"
        v-on:click="slide1On"
        v-bind:class="{ arrowright3on: isSlider3On }"
      >
        <i class="fas fa-chevron-right"></i>
      </div>
      <div
        class="arrowleft3"
        v-on:click="slide2On"
        v-bind:class="{ arrowleft3on: isSlider3On }"
      >
        <i class="fas fa-chevron-left"></i>
      </div>
      <div
        class="count1"
        v-bind:class="{ count1slide2: isSlider2On, count1slide3: isSlider3On }"
        v-on:click="slide1On"
      ></div>
      <div
        class="count2"
        v-bind:class="{ count2on: isSlider2On, count2slide3: isSlider3On }"
        v-on:click="slide2On"
      ></div>
      <div
        class="count3"
        v-bind:class="{ count3slide2: isSlider2On, count3on: isSlider3On }"
        v-on:click="slide3On"
      ></div>
    </div>
    <div
      class="gallerybtn"
      v-bind:class="{ open }"
      v-on:click="open = !open"
      ref="galbtn"
    >
      <div class="border1gal" v-bind:class="{ open }"></div>
      <div class="border2gal" v-bind:class="{ open }"></div>
      <h3 class="galtext" v-bind:class="{ open }">Testimonials</h3>
      <h3 class="goback" v-bind:class="{ open }">Go Back</h3>
    </div>
  </div>
</template>
<script>
import { gsap, TweenMax, TweenLite } from "gsap";
import Draggable from "gsap/Draggable";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
gsap.registerPlugin(Draggable);
gsap.registerPlugin(TweenMax);
gsap.registerPlugin(TweenLite);
export default {
  data: () => ({
    isWorkOn: true,
    isSlider2On: false,
    isSlider3On: false,
  }),
  inheritAttrs: true,
  props: ["open"],
  methods: {
    slide1On() {
      let reviews = this.$refs.reviews;
      this.isSlider2On = false;
      this.isSlider3On = false;
      TweenMax.to(reviews, 0, { x: 0 });
    },
    slide2On() {
      let reviews = this.$refs.reviews;
      this.isSlider2On = true;
      this.isSlider3On = false;
      TweenMax.to(reviews, 0, { x: -350 });
    },
    slide3On() {
      let reviews = this.$refs.reviews;
      this.isSlider3On = true;
      this.isSlider2On = false;
      TweenMax.to(reviews, 0, { x: -700 });
    },
  },
};
</script>
<style>
.section2 .about {
  text-align: center;
  font-size: 26px;
  line-height: 41px;
  font-family: "Raleway", sans-serif;
  margin-top: 100px;
  font-weight: 300;
  color: #0b3245;
  opacity: 0;
  user-select: none;
}
.gallerybtn {
  margin: 0 auto;
  width: 188px;
  height: 70px;
  margin-top: 110px;
  opacity: 0;
  position: relative;
  top: 20px;
}
.border1gal {
  border: 1px solid #0b3245;
  width: 188px;
  height: 70px;
  margin-top: 0px;
  margin-left: -4px;
  transition: 0.2s;
}
.border2gal {
  border: 1px solid #0b3245;
  width: 188px;
  height: 60px;
  margin-top: -67px;
  margin-left: 5px;
  transition: 0.2s;
}

.galtext {
  text-align: center;
  color: #0b3245;
  margin-top: -42px;
  font-family: Raleway;
  font-weight: 400;
  user-select: none;
  user-select: none;
}

.goback {
  text-align: center;
  color: #0b3245;
  margin-top: -41px;
  font-family: Raleway;
  font-weight: 400;
  user-select: none;
  user-select: none;
  margin-left: 5px;
  opacity: 0;
}

.galswitch {
  margin: 0 auto;
  width: 195px;
  height: 70px;
  margin-top: 140px;
  opacity: 0;
  z-index: +10;
  position: relative;
  margin-top: -48px;
  background: grey;
  z-index: -1;
  display: none;
}

.reviewcontainer.open {
  margin-top: 100px;
}
.galswitchon {
  z-index: +2;
  display: block;
}
.galtext.open {
  opacity: 0;
}
.goback.open {
  opacity: 1;
}
.reviewcontainer.open {
  transition: 0.5s;
  margin-top: 100px;
  display: block;
  opacity: 1;
  z-index: +1;
}
.slidercount.open {
  display: block;
}
.border1gal.open {
  margin-left: 5px;
}
.count2on {
  width: 30px;
  height: 6px;
  background: #0b3245;
  border-radius: 5px;
}
.count1slide2 {
  width: 5px;
  height: 5px;
  background: #b9c4ca;
  border-radius: 100%;
  margin-left: 24px;
}
.count3slide2 {
  margin-left: 71px;
  width: 5px;
  height: 5px;
  background: #b9c4ca;
  border-radius: 100%;
}
.count3on {
  width: 30px;
  height: 6px;
  background: #0b3245;
  border-radius: 5px;
  margin-top: -5.5px;
  margin-left: 59px;
}
.count1slide3 {
  width: 5px;
  height: 5px;
  background: #b9c4ca;
  border-radius: 100%;
  margin-left: 36px;
}
.count2slide3 {
  margin: 0 auto;
  border-radius: 100%;
  margin-top: -5.5px;
  width: 5px;
  height: 5px;
  background: #b9c4ca;
  transition: 0.3s;
  margin-top: -5px;
}
.arrowright1off {
  display: none;
}
.arrowleft1off {
  display: none;
}
.arrowright2on {
  display: block;
}
.arrowleft2on {
  display: block;
}
.arrowright3on {
  display: block;
}
.arrowleft3on {
  display: block;
}
</style>