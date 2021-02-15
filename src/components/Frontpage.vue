<template>
  <div class="frontpage">
    <header refs="header">
      <nav>
        <ul>
          <div class="logo" v-on:click="scrollIntoViewFront()">
            <img class="peregrine" src="../assets/Peregrinelogo.png" />
          </div>
        </ul>
      </nav>
    </header>
    <div class="frontbg">
      <div class="center-text">
        <div class="pictures">
          <div class="piccontainer1">
            <img class="scaff1" src="../assets/Scaff1.jpg" />
            <img class="scaff2" src="../assets/scaff2.jpg" />
            <img class="scaff4" src="../assets/scaff4.jpg" />
          </div>
        </div>
        <h2 class="ps">Peregrine Scaffolding<br />Brighton & Hove</h2>
        <div class="pssq"></div>
        <div class="buttons">
          <div class="view-site" v-on:click="scrollIntoViewAbout()">
            <div class="border1"></div>
            <div class="border2"></div>
            <h3 class="viewtext">View Site</h3>
          </div>
          <div class="contact" v-on:click="scrollIntoViewContact()">
            <h3 class="contacttext">Contact Us</h3>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {};
  },

  methods: {
    scrollIntoViewFront() {
      window.scrollTo(0, 0);
    },
    scrollIntoViewAbout() {
      window.scrollTo(0, 750);
    },
    scrollIntoViewContact() {
      window.scrollTo(0, 5000);
    },
  },
};
</script>
<style>
input,
select {
  vertical-align: middle;
}
header {
  height: 80px;
  background: #171717;
  width: 100%;
  display: block;
  top: 0;
  margin-bottom: -5px;
  padding: 2px;
  border: none;
}

header nav ul li {
  float: right;
  list-style: none;
  display: flex;
  padding: 4px;
}

header nav ul li a {
  font-size: 14px;
  color: white;
  padding: 10px;
  font-family: "Rubik";
  font-weight: 300;
  user-select: none;
}
.logo {
  height: 60px;
  width: 60px;
  position: fixed;
  background: #171717;
  z-index: +1;
  margin-top: -9px;
  margin-left: -25px;
}
.logotrigger {
  height: 60px;
  width: 60px;
  position: relative;
  background: #171717;
  z-index: +5;
  top: -290px;
  margin-top: -40px;
  opacity: 0;
  margin-left: -25px;
}
.peregrine {
  height: 35px;
  width: 40px;
  position: fixed;

  z-index: +30;
  margin-top: 12px;
  margin-left: 10px;
}
.burger {
  height: 66px;
  width: 66px;
  background: #0b3245;
  margin-top: -1000px;
  position: fixed;
  left: 76%;
  border-radius: 100%;
  z-index: +10;
}
.lineburg1 {
  margin: 0 auto;
  margin-top: 26px;
  width: 34px;
  height: 3px;
  background-color: #f6fcff;
  transition: 0.2s;
}
.lineburg2 {
  margin: 0 auto;
  margin-top: 10px;
  width: 34px;
  height: 3px;
  background-color: #f6fcff;
  transition: 0.2s;
}
.burgeroff {
  height: 40px;
  width: 70px;
  background: #2c3438;
  margin-top: -125px;
  position: fixed;
  left: 75%;
  opacity: 0;
  display: none;
  z-index: +5;
}
.burgermenu {
  width: 500%;
  height: 500%;
  left: 100%;
  top: 100%;
  border-radius: 3000%;
  position: fixed;
  background-color: #f6fcff;
  z-index: +3;
  transition: 0.4s;
  user-select: none;
}
.about2 {
  z-index: +3;
  font-family: Raleway;
  left: -50%;
  top: 40%;
  font-size: 35px;
  position: fixed;
  margin-top: 0;
  font-weight: 300;
  transform: translate(-50%, -50%);
  transition: 0.2s;
  user-select: none;
}
.reviews2 {
  z-index: +3;
  font-family: Raleway;
  left: -50%;
  top: 50%;
  margin-top: 0;
  font-size: 35px;
  position: fixed;
  font-weight: 300;
  transform: translate(-50%, -50%);
  transition: 0.2s;
  transition-delay: 0.05s;
  user-select: none;
}

.contact2 {
  z-index: +3;
  font-family: Raleway;
  left: -50%;
  top: 60%;
  margin-top: 0;
  font-size: 35px;
  position: fixed;
  font-weight: 300;
  transform: translate(-50%, -50%);
  transition: 0.2s;
  transition-delay: 0.1s;
  user-select: none;
}

.frontbg {
  margin-left: auto;
  margin-right: auto;
  display: table;
  background: #171717;
  width: 100%;
  height: calc(100vh - 75px);
}
.center-text {
  align-items: center;
  display: table-cell;
  vertical-align: middle;
}
.center-text h2 {
  flex-direction: column;
  justify-content: center;
  align-items: center;
  display: flex;
  color: white;
  font-family: "Raleway", sans-serif;
  font-weight: 400;
  font-size: 24px;
  line-height: 45px;
  margin-top: -340px;
  text-align: center;
  opacity: 0;
  position: relative;
  z-index: +2;
  user-select: none;
}

.pssq {
  width: 290px;
  height: 110px;
  background: #171717;
  position: relative;
  margin: 0 auto;
  z-index: 0;
  margin-top: -70px;
  border: 1px solid white;
}

.view-site {
  margin: 0 auto;
  width: 188px;
  height: 70px;
  margin-top: 110px;
  z-index: +2;
  position: relative;
}

.border1 {
  border: 1px solid white;
  width: 188px;
  height: 70px;
  margin-top: 0px;
  margin-left: -4px;
  background: #171717;
}

.border2 {
  border: 1px solid white;
  width: 188px;
  height: 60px;
  margin-top: -67px;
  margin-left: 5px;
}

.viewtext {
  text-align: center;
  color: white;
  margin-top: -42px;
  font-family: Raleway;
  font-weight: 400;
  user-select: none;
}
.contacttext {
  text-align: center;
  color: rgb(0, 0, 0);
  padding-top: 23px;
  font-family: Raleway;
  font-weight: 400;
  user-select: none;
}
.contact {
  margin: 0 auto;
  background: white;
  width: 192px;
  height: 70px;
  margin-top: 20px;
  position: relative;
}
.aboutintoviewtrigger {
  width: 20px;
  height: 20px;
  background: grey;
  opacity: 0;
}
.section2 .about {
  text-align: center;
  font-size: 25px;
  line-height: 39px;
  font-family: "Raleway", sans-serif;
  margin-top: 100px;
  font-weight: 300;
  color: #0b3245;
  opacity: 0;
  user-select: none;
}

.abouttrigger {
  width: 20px;
  height: 20px;
  margin-top: -80px;
  background: grey;
  opacity: 0;
}
.aboutline {
  margin: 0 auto;
  margin-top: 100px;
  width: 0px;

  height: 1px;
  background: #0b3245;
}

.pictures div {
  width: 320px;
  height: 480px;

  margin: 0 auto;

  -webkit-filter: grayscale(1000%);
  -moz-filter: grayscale(1000%);
  -ms-filter: grayscale(1000%);
  -o-filter: grayscale(1000%);
  overflow: hidden;
  display: block;
}

.pictures {
  transition: 0.5s;
  overflow: hidden;
  margin-top: -20px;
  opacity: 0.8;
}

.scaff1 {
  margin: 0 auto;
  width: 330px;
  height: 480px;
  opacity: 1;
  animation: scaff1 11s infinite;
  z-index: 1;
  margin-top: 000px;
  position: relative;
}

.scaff2 {
  margin: 0 auto;
  width: 700px;
  height: 500px;
  margin-left: -120px;
  margin-top: -400px;
  margin-bottom: 100px;
  position: relative;
  z-index: 1;
  opacity: 1;
  top: -20%;
  animation: scaff2 11s infinite;
}

.scaff4 {
  margin: 0 auto;
  margin: 0 auto;
  width: 380px;
  height: 540px;
  margin-top: -42px;
  margin-top: -350px;
  margin-bottom: 100px;
  position: relative;
  z-index: 1;
  top: -80%;
  animation: scaff4 11s infinite;
}

@keyframes scaff1 {
  0% {
    opacity: 1;
  }
  33% {
    opacity: 0;
  }
  66% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
@keyframes scaff2 {
  0% {
    opacity: 0;
  }
  33% {
    opacity: 0;
  }
  66% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}
@keyframes scaff4 {
  0% {
    opacity: 0;
  }
  33% {
    opacity: 1;
  }
  66% {
    opacity: 0;
  }
  100% {
    opacity: 0;
  }
}

.reviewcontainer {
  margin: 0 auto;
  margin-top: 120px;

  width: 320px;
  height: 300px;

  display: none;
  opacity: 0;
  overflow: hidden;
}

.reviewblock {
  width: 3200px;
  height: 100px;
  background: none;
  margin-left: -1390px;
  opacity: 1;
}

.name1 {
  text-align: center;
  font-family: Raleway;
  font-size: 22px;
  font-weight: 300;
  padding-bottom: 20px;
  user-select: none;
  margin-left: -100px;
}

.review1 {
  text-align: center;
  font-family: Raleway;
  font-size: 22px;
  font-weight: 300;
  line-height: 32px;
  user-select: none;
  margin-left: -100px;
}

.name2 {
  text-align: center;
  font-family: Raleway;
  font-size: 22px;
  font-weight: 300;
  padding-bottom: 20px;
  user-select: none;
  margin-left: 600px;
  margin-top: -222px;
}

.review2 {
  text-align: center;
  font-family: Raleway;
  font-size: 22px;
  font-weight: 300;
  line-height: 32px;
  user-select: none;
  margin-left: 600px;
  margin-top: 0px;
}

.name3 {
  text-align: center;
  font-family: Raleway;
  font-size: 22px;
  font-weight: 300;
  padding-bottom: 20px;
  user-select: none;
  margin-left: 1300px;
  margin-top: -258px;
}

.review3 {
  text-align: center;
  font-family: Raleway;
  font-size: 22px;
  font-weight: 300;
  line-height: 32px;
  user-select: none;
  margin-left: 1300px;
  margin-top: -20px;
}

.slidercount {
  margin: 0 auto;
  margin-top: -40px;
  opacity: 0;
  width: 100px;
  height: 25px;
  display: none;
}

.count1 {
  width: 30px;
  height: 6px;
  margin: 0 auto;
  border-radius: 5px;
  margin-left: 11px;
  margin-top: -15px;
  background: #0b3245;
  transition: 0.3s;
}

.arrowright1 {
  margin-top: 15px;
  margin-left: 190px;
  font-size: 25px;
  color: #0b3245;
}

.arrowleft1 {
  margin-top: -29px;
  margin-left: -105px;
  font-size: 25px;
  color: #0b3245;
}

.arrowleft2 {
  margin-top: -20px;
  margin-left: -105px;
  font-size: 25px;
  color: #0b3245;
  display: none;
}

.arrowright2 {
  margin-top: 15px;
  position: relative;
  top: 0px;
  margin-left: 190px;
  font-size: 25px;
  color: #0b3245;
  display: none;
}

.arrowleft2 {
  margin-top: -30px;
  margin-left: -105px;
  font-size: 25px;
  color: #0b3245;
  display: none;
}

.arrowright3 {
  margin-top: -29px;
  margin-left: 190px;
  font-size: 25px;
  color: #0b3245;
  display: none;
}

.arrowleft3 {
  margin-top: -29px;
  margin-left: -105px;
  font-size: 25px;
  color: #0b3245;
  display: none;
}

.count2 {
  margin: 0 auto;
  border-radius: 100%;
  margin-top: -5.5px;
  width: 5px;
  height: 5px;
  background: #b9c4ca;
  transition: 0.3s;
}

.count3 {
  margin: 0 auto;
  border-radius: 100%;
  margin-top: -5px;
  margin-left: 59px;
  width: 5px;
  height: 5px;
  background: #b9c4ca;
  transition: 0.3s;
}

.contactus {
  text-align: center;
  font-size: 42px;
  font-family: "Raleway", sans-serif;
  margin-top: 150px;
  font-weight: 300;
  color: #0b3245;
  white-space: nowrap;
  opacity: 0.8;
  user-select: none;
}
.emailbtn {
  margin: 0 auto;
  width: 178px;
  height: 70px;
  background: #0b3245;
  margin-top: 80px;
  opacity: 0.8;
}

.numberbtn {
  margin: 0 auto;
  width: 178px;
  height: 70px;
  border: 1px solid #0b3245;
  margin-top: 25px;
  margin-bottom: 80px;
  opacity: 0.8;
}

.emailtext {
  margin: 0 auto;
  color: white;
  text-align: center;
  font-weight: 300;
  font-family: Raleway;
  padding: 23px;
  user-select: none;
}

.numbertext {
  margin: 0 auto;
  color: #0b3245;
  text-align: center;
  font-weight: 300;
  font-family: Raleway;
  padding: 23px;
  user-select: none;
}

.phonenumber {
  margin: 0 auto;
  color: #0b3245;
  text-align: center;
  font-weight: 400;
  margin-top: -250px;
  font-family: Raleway;
  padding: 120px;
  font-size: 22px;
  user-select: none;
  opacity: 0.8;
  display: none;
}

.bounds {
  opacity: 1;
}
</style>
