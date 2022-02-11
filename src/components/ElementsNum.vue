<template>
        <div class="v_elementsNum">
            <button @click="operations(0)">+</button>
            <input @input="operations(2)" type="text" :value="cantidad"/>
            <button @click="operations(1)">-</button>
        </div>
</template>


<script>
      export default {
        name: 'ElementsNum',
        props:['itemElement'],
        data() {
            return {
                 cantidad:0,
                 checkedNames:[]
            }
        },
        methods:{
            operations: function(option){
                switch(option){
                    case 0:
                        if(this.cantidad >= 0)
                             this.cantidad++
                        break;
                    case 1:
                        if(this.cantidad > 0)
                            this.cantidad--;
                        break;
                    case 2:
                        if(this.cantidad < 0)
                           this.cantidad = 0;
                        else
                           this.cantidad = this.checkedNames[0];
                        break;
                    default:
                }   
            this.$emit('click_hijo',this.itemElement,this.cantidad);
 
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
}
div>label{
    margin-right:10px;
}

.v_elementsNum{
display:flex;
flex-direction:row;
justify-content: center;
flex-wrap:nowrap;
}

.v_elementsNum>p{
width:50px;
}

</style>