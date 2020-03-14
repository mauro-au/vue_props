<template>
  <div id="main">
    <h2>{{ message }}</h2>
    <br />
    <label>Tarea</label>
    <input type="text" v-model="tarea" @keyup.enter="guardarTarea"/>
    <button @click="guardarTarea">Agregar</button>
    <br />
    <AgregarLista :tareas="tareas" @antena= "borrarTarea"></AgregarLista>
  </div>
</template>

<script>
import AgregarLista from "./componentes/AgregarLista.vue";
export default {
  name: "App",
  components: { 
      AgregarLista 
    },
  data() {
    return {
      message: "Liata de Tareas",
      tarea: "",
      tareas: [],
      mostrar: false
    };
  },
  methods: {

    guardarTarea: function() {
        if(this.tarea !== ""){

            this.tareas.push({
              name: this.tarea
            });
        }
      this.tarea = "";
    },
      
		borrarTarea: function(index){
			this.tareas.splice(index,1);
		}
  }
};
</script>
<style scoped>
#main {
  font-size: 25px;
  font-family: "Calibri", sans-serif;
  color: darkblue;
  text-align: center;
}
button{
    padding: 10px 30px;
    background: #0e62ff;
    border-radius: 5px;
    border: none;
    color: #fff;
    cursor: pointer;
}
input{
    padding: 10px;
    margin: 0 10px;
    border-radius: 5px;
    border: 1px solid #ccc;
}

</style>