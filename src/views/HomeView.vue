<template>
  <b-container >
    <b-row align-v="center" cols="auto">
      <PlayerCardVue v-for="player in displayplayers" :key="player.id" :name="player.name" :img="player.img" :desc="player.desc" />
      

    </b-row>
    <b-pagination
      align="center"
      v-model="currentPage"
      :total-rows="rows"
      :per-page="perPage"
      first-text="First"
      prev-text="Prev"
      next-text="Next"
      last-text="Last"
      @input="paginate(currentPage)"
    ></b-pagination>
  </b-container>
</template>

<script>
// @ is an alias to /src

import { BContainer, BRow} from "bootstrap-vue";
import PlayerCardVue from '@/components/PlayerCard.vue';
export default {
  name: "HomeView",
  components: {
    BContainer,
    BRow,
    PlayerCardVue
  },
  mounted(){
this.fetchData();
  },
  data(){
    return{
      players:[],
      displayplayers:[],
      currentPage:1,
      rows:1,
      perPage:3
    }
  },
  methods:{
   async fetchData(){
    const res =await fetch("Players.json");
    const val =  await res.json();
    this.players= val;
    this.displayplayers= val.slice(0,3);
    this.rows=this.players.length;
    console.log(val);
   },
   paginate(currentPage){
    const start =(currentPage - 1)* this.perPage;
    this.displayplayers = this.players.slice(start,start +3);
   }
  }
};
</script>
