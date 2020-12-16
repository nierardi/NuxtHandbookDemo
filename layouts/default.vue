<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <a class="navbar-brand" href="/">CGA Handbook</a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item active">
            <a class="nav-link" @click="back" href="#">Home</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Login</a>
          </li>
        </ul>
      </div>
    </nav>
    <div class="container">
      <div class="row">
        <monographList v-show="showList" @mgClick="monographClick" />
      </div>
      <div class="row">
        <monographDetails v-show="showDetails" @backClick="back" :mg="mg" />
      </div>
    </div>
  </div>
</template>

<script>
import monographList from "~/components/monographList";
import MonographDetails from "~/components/monographDetails";
export default {
  components: {MonographDetails, monographList},
  data: () => {
    return {
      mg: null,
      showDetails: false,
      showList: true,
    }
  },
  methods: {
    monographClick(mg) {
      //alert("You clicked a monograph! " + mg.name);
      this.mg = mg;
      this.showDetails = true;
      this.showList = false;
    },
    back() {
      if (this.showDetails) {
        this.showDetails = false;
        this.showList = true;
      }
    }
  },
  mounted: () => {
    // Methods that execute on mount
    //document.addEventListener("backbutton", this.back, false)
    //window.onpopstate = () => this.back();
  },
}
</script>

<style>
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
