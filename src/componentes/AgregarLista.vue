<template>
    <div>
        <ul class="container">
            <li v-for="(tarea, index) in tareas" :key="index">
                {{tarea.name}}
                <button @click="enviarBorrado(index)">eliminar</button> 
            </li>
        </ul>

    </div>
</template>
<script>
    export default {
    name: "AgregarLista",
     props: {
      tareas: Array
      },

      methods:{
          enviarBorrado: function(index){
              this.$emit('antena', index)
          }
      }
};

</script>

<style scoped>

button{
    padding: 10px 30px;
    background: #0e62ff;
    border-radius: 5px;
    border: none;
    color: #fff;
    margin-left: 15px;
    cursor: pointer;
}
.container{
    width: 370px;
    margin: 30px auto 0 auto;
    text-align: left;
}
.container li{
    margin:20px;
}
</style>
