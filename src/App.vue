<template>
  <div id="app">

    <h2>Calculator in Vue JS</h2>
<b-navbar toggleable="md" type="dark" variant="info">

  <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>

  <b-navbar-brand href="#">NavBar</b-navbar-brand>

  <b-collapse is-nav id="nav_collapse">

    <b-navbar-nav>
      <b-nav-item href="#">Link</b-nav-item>
      <b-nav-item href="#" disabled>Disabled</b-nav-item>
    </b-navbar-nav>

    <!-- Right aligned nav items -->
    <b-navbar-nav class="ml-auto">

      <b-nav-form>
        <b-form-input size="sm" class="mr-sm-2" type="text" placeholder="Search"/>
        <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
      </b-nav-form>

      <b-nav-item-dropdown text="Lang" right>
        <b-dropdown-item href="#">EN</b-dropdown-item>
        <b-dropdown-item href="#">ES</b-dropdown-item>
        <b-dropdown-item href="#">RU</b-dropdown-item>
        <b-dropdown-item href="#">FA</b-dropdown-item>
      </b-nav-item-dropdown>

      <b-nav-item-dropdown right>
        <!-- Using button-content slot -->
        <template slot="button-content">
          <em>User</em>
        </template>
        <b-dropdown-item href="#">Profile</b-dropdown-item>
        <b-dropdown-item href="#">Signout</b-dropdown-item>
      </b-nav-item-dropdown>
    </b-navbar-nav>

  </b-collapse>
</b-navbar>

    <div class="">
      <input v-model="txt1" id="txt1" tytpe="number" class="form-control">
    </div>

    <br>
    <input v-model="txt2" id="txt2" type="number" class="form-control">
    <br>

 <select class="form-control" v-model="txt3">
        <option value="+">plus</option>
        <option value="-">minus</option>
        <option value="/">divided</option>
        <option value="*">multi</option>
      </select>


 <!--
 <input v-model="txt3" >
 -->

    <br>
<button class="btn btn-success btn-block" @click="calculate">Calculate</button>
<br><br>
<div class="result">
      <span>the result is...</span>
      <em v-if="txt3==='+'">{{sum}}</em>
       <em v-if="txt3==='-'">{{sub}}</em>
       <em v-if="txt3==='*'">{{mul}}</em>
       <em v-if="txt3==='/'">{{div}}</em>

    </div>
  </div>
</template>

<script>
export default {
  el: '#app',
  data () {
    return {
           txt1: 0,
                 txt2: 0,
                 txt3: '',
                 sum:'',
                 sub:'',
                 mul:'',
                 div:''


         }
  },

      methods: {
        calculate() {
          var txt1 = parseInt(this.txt1)
          var txt2 = parseInt(this.txt2)

          this.mul = txt1 * txt2
          this.sub = txt1 - txt2
          this.div = txt1 / txt2
          this.sum = txt1 + txt2
          this.txt3= this.txt3
        }
      }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
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
</style>
