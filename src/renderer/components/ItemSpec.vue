<template>
  <div class="container-fluid">
    <div class="row">
      <v-select placeholder="League" v-model="league" :options="leagues" data-live-search="true" :on-change="leagueSelectChange" class="col-md-4"></v-select>
      <!-- <div class="col-md-1"/> -->
      <v-select placeholder="Type" v-model="league" :options="leagues" class="col-md-4"/>
      <!-- <div class="col-md-1"/> -->
      <v-select placeholder="League" v-model="league" :options="leagues" class="col-md-4"/>
    </div>
    <div class="row">
      <div class="col-md-1"></div>
      <b-form-input v-model="itemName" type="text" placeholder="Item Name" class="col-md-10" />
      <div class="col-md-1"></div>
    </div>
    <div class="row">

    </div>
  </div>
</template>
<script>
//imports
import Vue from 'vue';
import Vuex from 'vuex';
import BootstrapVue from 'bootstrap-vue';
import VueSelect from 'vue-select';
import fs from 'fs';
import path from 'path';
//styles to load
import 'bootstrap/dist/css/bootstrap.css';
import 'bootstrap-vue/dist/bootstrap-vue.css';
export default {
  name: 'ItemSpec',
  components:{
    'v-select': VueSelect
  },
  props: {
    itemName: {
      type: String,
      default: '',
      required: false
    }
  },
  data(){
    return {
      leagues: JSON.parse(fs.readFileSync(path.join(__static,'data/leagues.json'), 'utf-8')),
      league:null
    };
  },
  methods:{
    leagueSelectChange(a){
      console.log(a);
    }
  }
}
</script>
<style lang="sass">
  $background-color: #303030;
  $font-list: 'Raleway', sans-serif;
  $text-color: #00BFFF;
  $backup-underline-color: #4EA6EA;
  $input-unfocused-underline: #5f5f5f;
  .v-select
    color: $text-color;
    font-family: $font-list;
    box-shadow: 0 10px 0 -7px $input-unfocused-underline;
    .open-indicator:before
      border-color: $backup-underline-color;
    input
      color: $text-color;
  .form-control,.form-control:focus
    color: $text-color;
  .dropdown-menu
    background: $background-color !important;
    color: $text-color;
</style>

<style lang="sass" scoped>
  $background-color: #303030;
  $font-list: 'Raleway', sans-serif;
  $text-color: #00BFFF;
  $backup-underline-color: #4EA6EA;
  $input-unfocused-underline: #5f5f5f;

  =border-radius($radius)
    -webkit-border-radius: $radius
    -moz-border-radius:    $radius
    -ms-border-radius:     $radius
    border-radius:         $radius
  select
    background: $background-color;
    border: 2px solid $input-unfocused-underline;
    color: $text-color;
    font: $font-list;
    -webkit-appearance: none;
    appearance: none;
    padding: 2px;
    margin-left:
  .dropdown-toggle
    color: white;
    background-color: red;
  
  input[type=text]
    border: 0;
    box-shadow: 0 10px 0 -7px $input-unfocused-underline;
    background: none;
    +border-radius(0);
    color: $text-color;
    -webkit-transition: box-shadow 0.3s;
    transition: box-shadow 0.3s;
  input[type=text]:focus
    box-shadow: 0 10px 0 -7px $text-color;
  
</style>
