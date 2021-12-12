<template>
  <div id="app">
    <h1>Lauro Cervantes</h1>
    <div class="s-services">
      <img id='images' alt="mua" :src=switchPic style="height: 620px; width:500px" @mouseover="onHover = true" @mouseleave="onHover = false">
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      recentImg: require('./assets/yo5.jpg'),
      earlierImg: require('./assets/yo3.jpeg'),
      onHover: false
    }
  },
  computed: {
    switchPic () {
      if (this.onHover == true) {
        return this.earlierImg
      } else {
        return this.recentImg
      }
    }
  }
}
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#images {
  border-radius: 10em;
}

h1, h2 {
  font-family: Rancho, serif;
  text-align: center;
}

.s-services {
  padding-top: 24rem;
  padding-bottom: 20rem;
  background-color: #1d1b37;
  position: relative;
}

.s-services__leftcol p.lead {
  max-width: 90%;
}

.s-services .vert-line {
  width: 2px;
  height: 20rem;
  background-color: #f9861a;
  -webkit-transform: translate3d(50%, 0, 0);
  transform: translate3d(50%, 0, 0);
  position: absolute;
  bottom: -20rem;
  left: 20px;
}


.services-list h5 {
  color: #ffffff;
}


.services-list__item-header h5 {
  font-family: "Gothic A1", sans-serif;
  font-weight: 400;
  font-size: 3.6rem;
  padding-left: 1.111em;
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


.is-active .services-list__item-header::after {
  -webkit-transform: rotate(225deg);
  transform: rotate(225deg);
}


@media screen and (max-width:1040px) {
  .s-services {
    height: 12rem;
    left: 16px;
  }

  .s-services__content .s-services__leftcol p.lead {
    max-width: none;
  }

}

@media screen and (max-width:800px) {
  .s-services {
    padding-top: 20rem;
  }

  .s-services__content .s-services__leftcol {
    -ms-flex: 0 0 100%;
    -webkit-box-flex: 0;
    flex: 0 0 100%;
    max-width: 100%;
  }

}

@media screen and (max-width:600px) {
  .s-services .vert-line {
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
  .s-services .vert-line {
    left: 24px;
  }

  .services-list__item-header h5 {
    font-size: 2.8rem;
  }
}

</style>
