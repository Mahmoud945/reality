<template>
  <div class="mb-3">
    <b-navbar toggleable="lg" type="dark" variant="dark">
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-navbar-brand href="#"><img class="logo" src="../assets/R4.jpg"></b-navbar-brand>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="mr-auto">
          <b-nav-item to="/">Home</b-nav-item>
          <b-nav-item to="about">About</b-nav-item>
         
        </b-navbar-nav>
       
        <b-form inline>
          <b-input-group >
            <b-form-input v-model="searchQuery"  placeholder="Search..."></b-form-input>
            <b-input-group-append>
              <b-button variant="outline-secondary" @click="search">Search</b-button>
            </b-input-group-append>
          </b-input-group>
        </b-form>
      </b-collapse>
    </b-navbar>
  </div>
</template>
<script>
// import { BNavForm,BFormInput,BButton } from 'bootstrap-vue';
export default {
    components:{
        
    },
  data() {
    return {
      searchQuery: "",
    };
  },
  
  methods: {
    search() {
      // Perform search functionality here
      console.log('Searching for:', this.searchQuery);
    },
  },
  computed:{
    filterplayers(){
        return this.players.filter(player=>player.name.includes(this.searchQuery));
    }
  }
};
</script>
<style>
.search-input {
  margin-left: 20px;
}
.logo{
    border-radius: 50%;
    width: 50px;
    height: 50px;
    margin-left: 20px;
}
@media (min-width: 992px){
    .navbar-expand-lg .navbar-nav .nav-link{
        padding-right:2.5rem !important;
    }
    
}
.btn-outline-secondary{
        margin-left: 10px !important;
    }
    .mb-3{
        position: relative;
        z-index: 99;
    }
</style>
