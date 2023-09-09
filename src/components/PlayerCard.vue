<template>
    <div>
        
        <b-col>
        <b-card
        align="center"
          :title="name"
          :img-src="img"
          img-alt="info"
          img-top
          tag="article"
          style="max-width: 19rem;"
          class="mb-4"
          
          
        >
          <b-card-text>
           
           {{ desc }}
          </b-card-text>
          <b-card-footer>
            <b-button v-b-modal.modal-lg variant="outline-primary" class="button-link">More</b-button>
            <b-modal id="modal-lg" size="lg" scrollable  title="Extra Large Modal">
                <b-col>
                <b-card
                    align="center"
                    :title="name"
                    :img-src="img"
                    img-alt="info"
                    img-left
                    tag="article"
                    style="max-width: 10rem;"
                    class="mb-4"
                 >
                 <b-card-text>           
                    {{ desc}}
                    25
                </b-card-text>
            </b-card>
                    </b-col>
                  <!-- <p class="my-2">
                    Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est voluptatum, fuga quo in officiis ratione tenetur vero quis laboriosam, numquam, repellat suscipit ipsam recusandae reiciendis soluta quidem expedita animi aut.
                  </p> -->
            </b-modal>
          </b-card-footer>
          
        </b-card>
      </b-col>
    </div>
</template>
<script>
import{BCol,BCard,BCardText,BButton}from 'bootstrap-vue'
export default{
    components:{
        BCol,
        BCard,
        BCardText,
        BButton
    },
    props:['name','img','desc']
}
</script>
<style>
.card{
    border-radius: 25px;
    height: 100%;
    border: none !important;
    width: 100%;
}

/* .card-img-top{
      width: 314px;
      max-width: 100%;
      height: 285px;
      flex-shrink: 0;
      object-fit: cover;
      border-radius: 25px 25px 0px 0px;
      
} */
/* .card-body{
    height: 190px;
      border-radius: 0px 0px 25px 25px;
      background:  #fff;
}  */
      /* .card-title {
      color:  #000;
      font-family: Poppins;
      font-size: 20px;
      font-style: normal;
      font-weight: 600;
      
    } */
/*     
    .card-footer {
      border: none !important;
      flex-wrap: wrap;
  
    } */
      /* .card-text {
        max-width: 262px;
        overflow-y: hidden;
        color: #5e5e5e;
        font-family: Poppins;
        font-size: 14px;
        font-style: normal;
        font-weight: 400;
      } */
      .button {
      font-size: 14px;
      font-weight: 600;
    }
      .button-link {
      color: #fff;
      /* border: none !important; */
      background: #fff;
      font-weight: 700 !important;
    }
    .button-link:hover {
      color:#fff !important;
    }
</style>
