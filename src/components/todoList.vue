<template>
    <div id="aqui">
        <h1>Lista de tareas</h1>
        <input v-model="tarea">
        <button @click="addTarea">Agregar</button>
         <h1>Lista</h1>
         <ul>
             <li v-for="(tarea, i) in tareas"
           :key="i">
                {{tarea}}
             </li>
         </ul>
    </div>
</template>


<script>
export default {
  name: 'todoList',
   data() {
       return {
         tarea: "",
        tareas:[]
    };
    
    },
    methods:{
        addTarea(){
            const tarea = this.tarea;
            this.tareas.push(tarea);
        }
    }
}




</script>