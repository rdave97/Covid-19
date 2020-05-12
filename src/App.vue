<template>
  <div>
    <b-navbar toggleable="lg" type="light" variant="white" class="pl-5  pr-3 one-edge-shadow">
      
      <b-navbar-brand href="#" @click="homeComp">
        <img :src="image" style="height: 50px; width: 299px;" />
      </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto pt-2"> 
          <b-nav-item class="link-nav" @click="homeComp">Home</b-nav-item>
          <b-nav-item class="link-nav" @click="USAComp">USA</b-nav-item>
          <b-nav-item class="link-nav last-nav" @click="indiaComp">India</b-nav-item>
        </b-navbar-nav>

        <!-- Right aligned nav items -->
          
            

            <!-- <b-nav-item-dropdown text="Lang" right>
              <b-dropdown-item href="#">EN</b-dropdown-item>
              <b-dropdown-item href="#">ES</b-dropdown-item>
              <b-dropdown-item href="#">RU</b-dropdown-item>
              <b-dropdown-item href="#">FA</b-dropdown-item>
            </b-nav-item-dropdown> -->

            <!-- <b-nav-item-dropdown right>
              
              <template v-slot:button-content>
                <em>User</em>
              </template>
              <b-dropdown-item href="#">Profile</b-dropdown-item>
              <b-dropdown-item href="#">Sign Out</b-dropdown-item>
        </b-nav-item-dropdown> -->
      </b-collapse>
    </b-navbar>
    
    <div>
      <Home v-if="home" class="pt-4"/>
      <USA v-if="USA" class="pt-4"/>
      <India v-if="india" class="pt-4"/>
    </div>
    
    
  </div>
</template>

<script>
  import Home from './components/Home.vue';
  import India from './components/India.vue';
  import image from './assets/image.png';
  export default {
    name: 'app',
    data () {
      return {
        image: image,
        home: true,
        india: false
      }
    },
    components:{
      Home: Home,
      India: India
    },
    methods: {
      homeComp()
      {
        this.home = true;
        this.india = false;
        console.log(this.home);
        console.log(this.india);
      },
      indiaComp()
      {
        this.india = true;
        this.home = false;
        console.log(this.home);
        console.log(this.india);
      }
    }
  }
</script>

<style>
  
    .link-nav{
      letter-spacing: 1px;
      padding-right: 15px;
      font-weight: 500;
    }
    .nav-bar{
      background-color: rgb(163, 175, 163);
    }
    .last-nav{
      padding-right: 50px;
    }
    .one-edge-shadow {
      -webkit-box-shadow: 0 6px 6px -6px rgba(146, 50, 50, 0.7);
      -moz-box-shadow: 0 6px 6px -6px rgb(0,0,0,0.7);
      box-shadow: 0 6px 6px -6px rgb(0,0,0,0.7);
    }
</style>
