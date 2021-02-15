<template>
  <div id="app">
    <front-page></front-page>
    <div
      class="burger"
      v-on:click="
        (burgerOn = !burgerOn), overflowOff(), burgerOff(), (openburg = true), (openreview = false)
      "
      v-bind:class="{ burgerOn }"
    >
      <div class="lineburg1" v-bind:class="{ burgerOn }"></div>
      <div class="lineburg2" v-bind:class="{ burgerOn }"></div>
    </div>

    <div class="burgermenu" v-bind:class="{ burgerOn }">
      <h2
        class="about2"
        v-bind:class="{ burgerOn }"
        v-on:click="scrollIntoViewAbout(), tagsOff()"
      >
        About.
      </h2>
      <h2
        class="reviews2"
        v-bind:class="{ burgerOn }"
        v-on:click="scrollIntoViewReviews(), tagsOff()"
      >
        Testimonials.
      </h2>
      <h2
        class="contact2"
        v-bind:class="{ burgerOn }"
        v-on:click="scrollIntoViewContact(), tagsOff()"
      >
        Contact.
      </h2>
      <div class="emailsq" v-bind:class="{ burgerOn }">
        <h3 class="emailname">peregrinescaffolding@gmail.com</h3>
      </div>
      <div class="phonesq" v-bind:class="{ burgerOn }">
        <h3 class="phonename">07519590262</h3>
      </div>
    </div>

    <section2 v-bind:openreview="openreview"></section2>
    <h1 class="contactus" ref="contact">Contact Us</h1>
    <div class="emailbtn" v-on:click="Email()">
      <h3 class="emailtext" v-bind:href="email">Email</h3>
    </div>
    <div class="numberbtn" v-on:click="Phone">
      <h3 class="numbertext">Phone</h3>
    </div>
    <h1 class="phonenumber" v-bind:class="{ phoneon: isPhoneOn }">
      07519590262
    </h1>
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
import FrontPage from "../src/components/Frontpage";
import Section2 from "./components/Section2.vue";


export default {
  name: "App",
  components: {
    FrontPage,
    Section2,
  },
  data: function () {
    return {
      isPhoneOn: false,
      burgerOn: false,
      openburg: false,
      openreview: false,
    };
  },

  methods: {
    scrollIntoViewAbout() {
      window.scrollTo(0, 700);
    },
    scrollIntoViewReviews() {
      window.scrollTo(0, 1000);
      this.openreview = true;
      if (this.openreview == true) {
        window.scrollTo(0, 1100);
      }
    },
    scrollIntoViewContact() {
      window.scrollTo(0, 5000);
    },
    overflowOff() {
      if (this.burgerOn == true) {
        let body = document.body;
        body.style.overflow = "hidden";
      }
    },
    burgerOff() {
      if (this.burgerOn == false) {
        this.burgerOn = false;
        let body = document.body;
        body.style.overflow = "auto";
      }
    },
    tagsOff() {
      this.burgerOn = false;
      let body = document.body;
      body.style.overflow = "auto";
    },
    Email() {
      window.open("mailto:peregrinescaffolding@gmail.com");
    },
    Phone() {
      if (
        navigator.userAgent.match(/Android/i) ||
        navigator.userAgent.match(/webOS/i) ||
        navigator.userAgent.match(/iPhone/i) ||
        navigator.userAgent.match(/BlackBerry/i) ||
        navigator.userAgent.match(/Windows Phone/i)
      ) {
        window.open("tel:07519590262");
      } else {
        this.isPhoneOn = true;
      }
    },
  },
  mounted: function () {
    this.aboutref = this.$refs["abt"];
    gsap.to(".ps", {
      scrollTrigger: {
        trigger: ".ps",
      },
      opacity: "1",
      y: +50,
    });
    gsap.to(".about", {
      scrollTrigger: {
        trigger: ".abouttrigger",
      },
      opacity: "1",
      y: +0,
      transition: "0.25s",
    });
    gsap.to(".aboutline", {
      scrollTrigger: {
        trigger: ".aboutline",
      },
      opacity: "1",
      width: "50px",
    });
    gsap.to(".gallerybtn", {
      scrollTrigger: {
        trigger: ".gallerybtn",
      },
      opacity: "1",
      transition: "0.5s",
    });
    gsap.to(".reviewcontainer", {
      scrollTrigger: {
        trigger: ".reviewcontainer",
      },
      opacity: "1",
      transition: "0.5s",
    });
    gsap.to(".slidercount", {
      scrollTrigger: {
        trigger: ".reviewcontainer",
      },
      opacity: "1",
      transition: "0.5s",
    });
    gsap.to(".contactus", {
      scrollTrigger: {
        trigger: ".contactus",
      },
      opacity: "1",
      transition: "0.5s",
    });
    gsap.to(".emailbtn", {
      scrollTrigger: {
        trigger: ".emailbtn",
      },
      opacity: "1",
      transition: "0.25s",
    });
    gsap.to(".numberbtn", {
      scrollTrigger: {
        trigger: ".numberbtn",
      },
      opacity: "1",
      transition: "0.25s",
    });
    gsap.to(".burger", {
      scrollTrigger: {
        trigger: ".about",
        toggleActions: "restart none none reset",
      },
      opacity: "1",
      y: +860,
    });
    gsap.to(".logo", {
      scrollTrigger: {
        trigger: ".logotrigger",
        toggleActions: "restart none none reset",
      },
      opacity: "1",
      background: "#0B3245",
    });
  },
};
</script>

<style>
* {
  text-decoration: none;
}

html {
  scroll-behavior: smooth;
}
#app {
  overflow: hidden;
}
body {
  background-color: #f6fcff;
  margin: 0;
  padding: 0;
  overflow-x: hidden;
}
.burger.burgerOn {
  background-color: #f6fcff;
}
.lineburg1.burgerOn {
  transform: rotate(40deg);
  background: #0b3245;
  transition: 0.2s;
  margin-top: 35px;
}
.lineburg2.burgerOn {
  transform: rotate(-40deg);
  background: #0b3245;
  transition: 0.2s;
  margin-top: -3px;
}
.burgerswitch.burgerOn {
  z-index: +12;
  display: block;
}
.burgermenu.burgerOn {
  left: -300%;
  top: -300%;
}
.about2.burgerOn {
  left: 50%;
}
.reviews2.burgerOn {
  left: 50%;
}
.contact2.burgerOn {
  left: 50%;
}

.phoneon {
  margin-top: -180px;
  opacity: 1;
  display: block;
}

.emailname {
  z-index: +3;
  font-family: Raleway;
  left: 50%;
  top: 50%;
  margin-top: 0;
  font-size: 14px;
  position: fixed;
  font-weight: 300;
  transform: translate(-50%, -50%);
  transition: 0.2s;
  transition-delay: 0.1s;
  user-select: none;
  color: white;
}

.emailsq {
  width: 230px;
  height: 35px;
  background: #0b3245;
  transform: translate(-50%, -50%);
  position: fixed;
  left: -200px;
  top: 90%;
  transition: 0.2s;
}

.emailsq.burgerOn {
  left: 130px;
}

.phonename {
  z-index: +3;
  font-family: Raleway;
  left: 50%;
  top: 50%;
  margin-top: 0;
  font-size: 14px;
  position: fixed;
  font-weight: 300;
  transform: translate(-50%, -50%);
  transition: 0.2s;
  transition-delay: 0.1s;
  user-select: none;
  color: white;
}

.phonesq {
  margin-top: 40px;
  width: 130px;
  height: 35px;
  background: #0b3245;
  transform: translate(-50%, -50%);
  position: fixed;
  left: -200px;
  top: 90%;
  transition: 0.2s;
}

.phonesq.burgerOn {
  left: 80px;
}

@media only screen and (min-width: 1030px) {
  .center-text h2 {
    font-size: 35px;
    line-height: 65px;
    margin-top: -555px;
    left: -235px;
    top: 150px;
    text-align: inherit;
  }
  .view-site {
    margin: 0 auto;
    width: 188px;
    height: 70px;
    margin-top: 120px;
    z-index: +2;
    top: 110px;
    left: -321px;
    position: relative;
  }
  .viewtext {
    text-align: center;
    color: white;
    margin-top: -32px;
    font-family: Raleway;
    font-weight: 400;
    user-select: none;
    margin-left: -36px;
    font-size: 14px;
  }
  .contacttext {
    text-align: center;
    color: rgb(0, 0, 0);
    padding-top: 23px;
    font-family: Raleway;
    font-weight: 400;
    user-select: none;
    position: relative;
    top: -4px;
    font-size: 14px;
  }
  .border1 {
    border: 1px solid white;
    width: 130px;
    height: 55px;
    margin-top: 0px;
    margin-left: 5px;
    background: #171717;
  }
  .border2 {
    border: 1px solid white;
    width: 130px;
    height: 45px;
    margin-top: -52px;
    margin-left: 15px;
  }
  .contact {
    margin: 0 auto;
    background: white;
    width: 130px;
    height: 55px;
    left: -180px;
    top: 20px;
    margin-top: 20px;
    position: relative;
  }
  .pssq {
    display: none;
  }
  .pictures div {
    margin: 0 auto;
    position: relative;
    left: 220px;
    width: 330px;
    height: 460px;

    opacity: 1;
  }
  .pictures {
    opacity: 1;
    margin-top: -210px;
    position: relative;
    left: -25px;
  }
  .scaff1 {
    width: 410px;
    height: 550px;
  }
  .scaff2 {
    width: 800px;
    height: 600px;
    top: -50%;
  }
  .scaff4 {
    width: 450px;
    height: 620px;
    top: -120%;
  }
}
</style>
