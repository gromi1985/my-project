<template>
  <div>
   <h1>{{ msg }}</h1>
   <div id="v-model-multiple-checkboxes">
      <input type="checkbox" id="valor_1" value="500" v-model="checkedNames" @change="sumaImportes(1)" />
      <label for="valor_1">Una página web (500€)</label><br>
      <Panel v-show="mostrar"> </Panel>
      <input type="checkbox" id="valor_2" value="300" v-model="checkedNames" @change="sumaImportes(0)" />
      <label for="valor_2">Una consultoria SEO (300€)</label><br>
      <input type="checkbox" id="valor_3" value="200" v-model="checkedNames"  @change="sumaImportes(0)"/>
      <label for="valor_3">Una campaña de Google Ads(200€)</label><br>
    </div>
    <br />
    <span>Preu: {{ total }}</span>
  </div>
</template>

<script>
import Panel from '@/components/Panel.vue'

export default {
      name: 'HelloWorld',
      components: {
        Panel
      },
      data() {
          return {
            checkedNames: [],
            total:0,
            mostrar:false
          }
      },
      methods:{
         sumaImportes: function(option){
            if(option)
              this.mostrar = !this.mostrar;
            this.total=0;
            for(let e of this.checkedNames)
              this.total += Number(e);
         }
      }
 }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

div>input {
margin:15px;
}
</style>
