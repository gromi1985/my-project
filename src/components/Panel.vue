<template>
   <div id="v-model-values" >
        <div class="line_element">
            <label for="imput_1">Numero de páginas</label>
            <ElementsNum id="firstElement" itemElement=0   @click_hijo="addTotal"></ElementsNum>
        </div>

        <br>
        <div class="line_element">
            <label for="imput_2">Numero de idiomas</label>
            <ElementsNum id="secondElement" itemElement=1  @click_hijo="addTotal"></ElementsNum>
        </div>
    </div>
</template>

<script>
import ElementsNum from '@/components/ElementsNum.vue'

export default {
  name: 'Panel',
  components: {ElementsNum},
      data() {
        return {
          itemOption: [0,0],
          total:0
        }
      },
  methods:{
            addTotal: function(itemElement,cantidad){
            this.itemOption[itemElement] = cantidad;
            this.$emit('click_padre',this.itemOption);

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

