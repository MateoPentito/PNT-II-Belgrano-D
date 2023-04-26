<template>

    <div>
        Agregar Nombre: <input type="text" v-model="elemento.nombre">
        Agregar Apellido: <input type="text" v-model="elemento.apellido">
        Agregar Edad: <input type="number" v-model="elemento.edad">
    <button v-on:click="agregarPersona">Agregar a la lista</button>
    </div>
    

</template>

<script>
export default {
    data(){
        return{
            elemento:{}
        }
    },
    methods:{
        agregarPersona(){
            this.$emit('Agregar',{...this.elemento})
        }
    }

}
</script>

<style>

</style>