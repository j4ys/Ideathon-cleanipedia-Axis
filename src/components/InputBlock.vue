<template>
  <div class="input">
 <div class="sel">
  <label for="select_state">States</label>
    <select v-model='state'  @change='getCitiesofState()'>
          <option value='0' selected >Select State</option>
          <option v-for='data in states' :value='data.region'>{{ data.region }}</option>
        </select>
 </div>
 <div class="sel">
  <label for="select_city">City</label>
<select v-model='city' >
          <option value='0' selected>Select City</option>
          <option v-for='data in cities' :value='data.city'>{{ data.city }}</option>
        </select>
 </div>
 <div class="sel">
  <label for="date_from">Date From</label>
    <input type="date" name="date_from" id="date_from">
 </div>
  <div class="sel">
   <label for="date_to">Date To</label>
    <input type="date" name="date_to" id="date_to">
 </div>
 <div class="sel">
    <button name="submit">Submit</button>
 </div>
  </div>
</template>

<script>
import axios from "axios";
import $ from 'jquery';
const api_key = "32f918baa556efdffec43246f9137d9a&callback=?";
export default {
  name: "InputBlock",
  data: () => {
     return { 
       states: null,
      state: '',
      city: '',
      cities: null
     }
  },

  created() {
    console.log("this is this = ", this)
    this.getstates();
  },

methods: {
    getstates() {
      let url = `https://battuta.medunes.net/api/region/in/all/?key=${api_key}?`
        $.getJSON(url,
        (data) => {
          this.states = data;
        } 
        )
        },
    getCitiesofState() {
      let st = this.state;
      let url = `https://battuta.medunes.net/api/city/in/search/?region=${st}&key=${api_key}`;
      $.getJSON(url,
        (data) => {
          this.cities = data;
        } 
        )
    }
  },
};
</script>
<style scoped>
button {
  height: 100px;
  width: 100%;
  background-color: #009688;
  color: white;
  margin: 20px;
  border: none;
  cursor: pointer;
  font-family: Cuprum;
}
.sel {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 10px;
}

.sel label {
  font-family: Cuprum;
  background-color: #009688;
  width: 100%;
  color: white;
  text-align: center;
}

.input {
  display: flex;
  grid-row: 2 / 3;
  justify-content: space-around;
}
select {
  height: 50px;
  border: none;
  outline: none;
  background-color: #009688;
  color: white;
  font-size: 15px;
  padding: 10px;
  overflow-y: hidden;
  max-width: 200px;
  min-width: 200px;
}

option {
  margin: 20px;
}

input[type="date"] {
  outline: none;
  border: none;
  background-color: #009688;
  height: 50px;
  font-size: 15px;
  color: white;
  padding: 0 10px;
}
input[type="date"]::-webkit-inner-spin-button {
  -webkit-appearance: none;
  display: none;
}
input[type="date"]::-moz-inner-spin-button {
  -moz-appearance: none;
  display: none;
}
0 input[type="date"]::-webkit-calendar-picker-indicator,
input[type="date"]::-moz-calendar-picker-indicator {
  color: white;
}

input[type="date"]::-webkit-calendar-picker-indicator:hover,
input[type="date"]::-moz-calendar-picker-indicator:hover {
  color: transparent;
}

input::-webkit-calendar-picker-indicator:hover,
input::-moz-calendar-picker-indicator:hover {
  background: transparent;
  cursor: pointer;
}
input::-webkit-clear-button:hover {
  color: white;
  opacity: 1;
}
</style>
