<template>
    <div id="aqui">
        <h1>Lista de tareas</h1> 
        <input v-model="tarea">
        <button @click="addTarea">Agregar</button>
         <h1>Lista</h1>
      <section v-if="tareas.length > 0">
                <eliminarList :tareas="tareas" @eliminarTarea="eliminarTarea"/>
      </section>
    </div>
</template>


<script>
import eliminarList from "@/components/eliminarList.vue";


export default {
 
  name: 'todoList',
  components:{
      eliminarList,
  },
   data() {
       return {
         tarea: "",
        tareas:[],
    };
    
    },
    methods:{
        addTarea(){
            const {tarea} = this;
            this.tareas.push(tarea);
        },
          eliminarTarea(indexTarea){
           this.tareas.splice(indexTarea, 1);
        },
      
    },
}


</script>