<template>
    <div >
        <ul>
         <li v-for="(tarea, i) in tareas" :key="i">
                    {{tarea}}
           <button @click="eliminarTarea(i)">Eliminar</button>   
         </li>
         
        </ul>
     
       
    </div>
</template>


<script>
export default {
  name: 'eliminarList',
  props: {
    tareas:[],
  },
    methods:{
      
        eliminarTarea(index){
           this.$emit("eliminarTarea", index)
        },
    },
}




</script>