<template>
  <div id="app">
    <h1 id="locals">{{title}}</h1>
    <h2 id="locals2" @mouseover="subTitle = salute">{{subTitle}}</h2>
    <button id="btn" @mouseover= "button = btnSwitch" @mouseleave="button='Load'" v-on:click="alert()">{{button}}</button>
    <div class="s-services">
      <h2 id="storie" @mouseover="fam=familie" @mouseleave="fam=null">{{fam}}</h2>
      <img id='images' alt="mua" :src=switchPic style="height: 620px; width:500px" @mouseover="onHover = true" @mouseleave="onHover = false">
      <img id='images2' alt="mua" :src=getBack style="height: 620px; width:500px" @mouseover="mouseOn = true" @mouseleave="mouseOn = false">
    </div>
  </div>
</template>

<script>
import dedication from './assets/dedication.json';

export default {
  name: 'App',
  data() {
    return {
      recentImg: require('./assets/yo5.jpg'),
      earlierImg: require('./assets/yo3.jpeg'),
      fam1: require('./assets/papas.jpeg'),
      fam2: require('./assets/yo4.jpeg'),
      onHover: false,
      mouseOn: false,
      title: "Lauro Cervantes",
      subTitle: "- * Portrait of a Loving Family * -",
      button: "Load",
      btnSwitch: "Click Here!",
      salute: "Hello Pal! Welcome to My Website!",
      fam: null,
      familie: "Martha Sanchez and Lauro Cervantes, You're the best Parents ever!"
    }
  },
  computed: {
    switchPic () {
      if (this.onHover == true) {
        return this.earlierImg
      } else {
        return this.recentImg
      }
    },
    getBack () {
      if (this.mouseOn == true ) {
        return this.fam2
      } else {
        return this.fam1
      }
    },
  },
  methods: {
    alert: function () {
      this.fam = dedication.story;
    }
  }
}
</script>

<style>

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
#images{
  border-radius: 10em;
  border-style: dotted;
  border-color: rgba(210, 175, 238, 0.96);
  margin-right: 25px;
}

#images2{
  border-radius: 10em;
  border-style: dotted;
  border-color: rgba(210, 175, 238, 0.96);
  margin-left: 25px;
}


.s-services {
  padding-top: 5rem;
  padding-bottom: 20rem;
  background-color: #1d1b37;
  position: relative;
}

.services-list h5 {
  color: #ffffff;
}


.services-list__item-header h5 {
  font-family: "Gothic A1", sans-serif;
  font-weight: 400;
  font-size: 3.6rem;
  margin: 0;
  position: relative;
}

.services-list__item-header h5::before {
  content: counter(ctr, decimal-leading-zero) ".";
  counter-increment: ctr;
  font-family: "Work Sans", sans-serif;
  font-weight: 600;
  font-size: .5em;
  line-height: 1;
  color: #f9861a;
  position: absolute;
  top: .5em;
  left: 0;
}


@media screen and (max-width:1040px) {
  .s-services {
    height: 12rem;
    left: 16px;
  }

  .s-services__content .s-services__leftcol p{
    max-width: none;
  }

}

@media screen and (max-width:800px) {
  .s-services {
    padding-top: 20rem;
  }

}

@media screen and (max-width:600px) {
  .s-services  {
    left: 34px;
  }

  .services-list__item-header h5 {
    font-size: 3.2rem;
  }

}

@media screen and (max-width:500px) {
  .services-list__item-header h5 {
    font-size: 3rem;
  }

}

@media screen and (max-width:400px) {
  .s-services {
    left: 24px;
  }

  .services-list__item-header h5 {
    font-size: 2.8rem;
  }
}
#locals {
  font-family: Rancho, serif;
  text-align: center;
  font-size: 80px;
}

#locals2{
  font-family: Rancho, serif;
  text-align: center;
  font-size: 40px;
}

#storie {
  font-family: Rancho, serif;
  text-align: center;
  font-size: 40px;
  color: white;
  padding-bottom: 5rem;
}

#btn{
  font-size: 30px;
  font-family: Rancho, serif;
  color: white;
  background-color: #1d1b37;
  border-radius: 30em;
}

#btn:hover {
  color: rgb(251, 255, 128);
}

</style>
