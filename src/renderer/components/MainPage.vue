<template>
  <div id="wrapper">
    <div id="title">le watch</div>
    <div id="content-wrapper" class="container-fluid">
      <div class="row">
        <div id="sidebar-wrapper" class="col-md-4">
          <item-spec></item-spec>
        </div>
        <div id="item-list-wrapper" class="col-md-8">
          <item-list></item-list>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import Vuex from 'vuex'
import BootstrapVue from 'bootstrap-vue'
import ItemList from './ItemList'
import ItemSpec from './ItemSpec'
//styles to load
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

Vue.use(Vuex);
Vue.use(BootstrapVue);
export default {
  name: 'MainPage',
  components: {
    'item-list': ItemList,
    'item-spec': ItemSpec
  }
}
</script>

<style>
  @font-face {
    font-family: 'Raleway';
    src: url('../assets/fonts/Raleway-Medium.ttf') format('truetype');
  }
</style>

<style lang="sass">
  $font-list: 'Raleway', sans-serif;

  #wrapper
    height: 100%;
    background: #303030;
    color: #00BFFF;
    font-family: 'Raleway', sans-serif;
  #title
    height: 1.75em;
    font-weight: bold;
    text-align: center;
    font-size: 3em;
    width: 100%;
  #sidebar-wrapper
    height: 20em;
    width: 30%;
    border: 1px solid black;
    resize: both;
  #item-list-wrapper
    height: 20em;
    width: 30%;
    border: 1px solid black;
    resize: both;
</style>
