<template>
  <div>
    <h1>{{ msg }}</h1>
    <h2>Lighting</h2>
    <button :class="classname" v-if="lights" v-on:click="lightsOff()">
      POOL LIGHTS
    </button>
    <button :class="classname" v-else v-on:click="lightsOn()">
      POOL LIGHTS
    </button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Caribbean Courtyard Villa",
  getHoursCondition: String,
  lights: false,
  classname: "on",
  props: {
    msg: String,
  },

  ///////////////////////////////////////////////////////////////////////////////
  //  DATA
  ///////////////////////////////////////////////////////////////////////////////
  data() {
    return {
      hours: new Date().getHours(),
      getHoursCondition: "", //define the variable first
      lights: false,
      classname: "on",
      outlet: {},
    };
  },

  ///////////////////////////////////////////////////////////////////////////////
  //  METHODS
  ///////////////////////////////////////////////////////////////////////////////
  methods: {
    lightsOn() {
      this.lights = true;
      this.classname = "on";
    },
    lightsOff() {
      this.lights = false;
      this.classname = "off";
    },
  },

  ///////////////////////////////////////////////////////////////////////////////
  //  MOUNTED
  ///////////////////////////////////////////////////////////////////////////////
  mounted() {
    this.classname = "off";
    this.lights = false;

    let access_token = "Y2hpbmFzcHJvdXQ";
    let url = "http://192.168.1.100/restapi/relay/outlets/=0,1,4/state/";

    const config = {
      headers: { Authorization: `Bearer ${access_token}` },
    };

    axios.get(url, config).then(console.log).catch(console.log);
  },
};
</script>

<style>
h1 {
  font-size: 3em;
  color: #fff;
}

h3 {
  margin: -140px 0 100 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

button {
  background-color: #F1C232;
  width: 300px;
  border: none;
  color: #fff;
  padding: 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 26px;
  margin: 54px 2px;
  border-radius: 35px;
  cursor: pointer;
}

.on {
  opacity: 1;
  box-shadow: 0 5px 15px rgba(255, 255, 255, 1);
}
.off {
  opacity: 0.9;
}
</style>
