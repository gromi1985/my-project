<template>
        <div class="v_elementsNum">
            <button @click="operations(0)">+</button>
            <input type="text" :value="cantidad"/>
            <button @click="operations(1)">-</button>
        </div>
</template>


<script>
      export default {
        name: 'ElementsNum',
        data() {
            return {
                 cantidad:0
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
                    default:
                }
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