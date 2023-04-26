<template>
  <div>
    <p> Lista de Proyectos</p>
    <li v-for="proy in proyectos" v-bind:key="proy.id">
        {{proy.id}} {{proy.desc}}
    </li>
    <button v-on:click="ordenarPorId">Ordenar por id </button>
    <br/>
    <ProyectoDetalle @agregarAlista="agregarProyecto"/>
  
  </div>
</template>

<script>
import ProyectoDetalle from './ProyectoDetalle.vue'
export default {
    components: {ProyectoDetalle},
    data() {
        return {
            proyectos: [{id:1,desc:'Marketing whatsapp'},
                        {id:2,desc:'Gestion Carta'},
                        {id:3,desc:'CRM consulta api'}],

            //Un objeto para cargar los datos de un proyecto, es vacio para cuando le mandes datos se ingresan en la lista de proyectos
        
        }
    },
    methods: {
        agregarProyecto(elemento) {
            //Validacopmes de INPUT
            this.proyectos.push(elemento)
           
        },
        ordenarPorId(){
            this.proyectos.sort((a,b)=>a.id-b.id)
        }
    }
}
</script>


<style>

</style>