<template>
   <div id="v-model-values" >
        <div class="line_element">
            <label for="imput_1">Numero de páginas</label>
            <ElementsNum id="firstElement"></ElementsNum>
        </div>

        <br>
        <div class="line_element">
            <label for="imput_2">Numero de idiomas</label>
            <ElementsNum id="secondElement"></ElementsNum>

        </div>
    </div>
</template>

<script>
import ElementsNum from '@/components/ElementsNum.vue'

export default {
  name: 'Home',
  components: {ElementsNum},
      data() {
        return {
          checkedNames: [],
          total:0
        }
      },
      methods:{
          sumaImportes: function(){
          this.total=0;
          for(let e of this.checkedNames)
              this.total += Number(e);
          }
      }
}
</script>

<style>
#v-model-values{
display:flex;
flex-direction:column;
justify-content: center;
align-items: center;
 border: 3px solid red;
 padding: 25px 15px;
 border-radius: 10px;
 width:400px;
 margin:20px;
}
div>label{
margin-right:10px;
}

.line_element{
display:flex;
flex-direction:row;
justify-content: center;
align-items: center;
}
</style>

