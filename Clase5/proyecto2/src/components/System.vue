<template>
  <div>
    Lista de personas
    <li v-for="per in personas" v-bind:key="per.nombre" > 
        {{per.nombre}} {{per.apellido}} {{per.edad}}
    </li>
    <br/>
    <Detail @Agregar="AgregarElemento"/>

  </div>
</template>

<script>
    import Detail from './Detail.vue'
export default {
    components:{Detail},
    data(){
        return{
            personas: [{nombre:"mateo",apellido:"pentito",edad:23},
            {nombre:"morena",apellido:"pentito",edad:24},
            {nombre:"martina",apellido:"pentito",edad:26}]
        }
    },
    methods: {
        AgregarElemento(elemento){
            this.personas.push(elemento)
        }

    }
}
</script>

<style>

</style>