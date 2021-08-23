<template>
    <button @click="accion" :disabled="desactivar">{{ texto }}</button>
</template>

<script>
export default {
    name:"AccionSaldo",
    props:{
        texto : String,
        desactivar: { 
            //Es es si deseamos que un elemento del props tenga un valor por defecto
            type: Boolean,
            default: false
        }
    },
    methods:{
        accion(){
            this.$emit('accion')
        }
    }
}
</script>

<style>

</style>