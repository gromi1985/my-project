<template>
<div class="bloqueGeneral">
  <div class="home">
    <h2> "Qué quieres hacer?" </h2>
    <div id="v-model-multiple-checkboxes">
      <div>
        <input type="checkbox" id="valor_1" value="500" v-model="checkedNames" @change="sumaImportes(1)" />
        <label for="valor_1">Una página web (500€)</label>
      </div>
    <br>
     <div>
        <Panel v-show="mostrar" @click_padre="totalImportes"> </Panel>
        <input type="checkbox" id="valor_2" value="300" v-model="checkedNames" @change="sumaImportes(0)" />
        <label for="valor_2">Una consultoria SEO (300€)</label>
     </div>

     <br>
     <div>
        <input type="checkbox" id="valor_3" value="200" v-model="checkedNames"  @change="sumaImportes(0)"/>
        <label for="valor_3">Una campaña de Google Ads(200€)</label>
     </div>
     <br>
    </div>
    <br />
    <span>Preu: {{ total }}</span>
  </div>

  <button id="buTTomBack">
      <router-link to="/Welcome">Back</router-link> 
   </button> 
   </div>
</template>

<script>
// @ is an alias to /src
import Panel from '@/components/Panel.vue'

export default {
  name: 'Home',
  components: {Panel},
  data() {
          return {
            checkedNames: [],
            total:0,
            mostrar:false,
            quantitys:[],
          }
      },
      methods:{
        totales:function(){
            this.total=0;
            for(let e of this.checkedNames)
              this.total += Number(e);
            for(let e of this.quantitys)
                this.total += (e*30);
         },
         sumaImportes: function(option){
            if(option)
              this.mostrar = !this.mostrar;
            this.totales();
         },
        totalImportes:function(arrayQuantities){
            this.quantitys = arrayQuantities;
            this.totales();
          }

      }
 }
</script>
<style>
#v-model-multiple-checkboxes{
display:flex;
flex-direction:column;
width: 400px;
}

.home{
border-style: ridge ;
width:70%;
margin:0 auto;
padding:15px;
text-align:start;
}

.bloqueGeneral{
font-size:20px;
width:70%;
display:flex;
flex-direction:column;
align-items:center;
}

#buTTomBack{
width:10%;
}

</style>

