<template>
    <h2>Tipo de cuenta: {{cuenta}}</h2>
    <h2>Saldo: {{saldo}}</h2>
    <h2>Cuenta: {{estado? 'Activa':"Desactivada"}}</h2>
    <div v-for="(item,index) in servicios" :key="item.id">
        {{index+1}}.- {{ item }}
    </div>
    <AccionSaldo texto="Aumentar saldo" @accion="aumentar"/>
    <AccionSaldo texto="Disminuir saldo" @accion="disminuir" :desactivar="desactivar"/>
</template>

<script>
import AccionSaldo from './AccionSaldo.vue'
export default {
    name:"Cuenta",
    data(){
        return {
            saldo:100,
            cuenta:'Visa',
            estado: false,
            servicios: ['Giro','Abono','Transfrencia'],
            desactivar: false
        }
    },
    components:{
        AccionSaldo
    },
    methods:{
        aumentar(){
            this.desactivar = false
            this.saldo += 100
        },
        disminuir(){
            if(this.saldo === 0){
                alert("El saldo agotado");
                this.desactivar = true;
                return
            }
            this.saldo -= 100
        }
    }
}
</script>

<style>

</style>