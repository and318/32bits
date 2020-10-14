<template>
    <div>
    <h4>Cantidad de Juegos con stock:{{totalJuegosstock}} </h4>

        <table class="table">
        <thead>
            <tr>
                <th>Código</th>
                <th>Nombre</th>
                <th>Stock</th>
                <th>Precio</th>
                <th></th>
                
            </tr>
        </thead>
        <tbody>
            <tr v-for="juego in JuegosParaVender" :key="juego.codigo" :style="{background:juego.color,color:juego.font}">
                <th>{{juego.codigo}}</th>
                <td>{{juego.nombre}}</td>
                <td>{{juego.stock}}</td>
                <td>{{juego.precio}}</td>
                <td><button @click="vender(juego)">Vender</button></td>
                
            </tr>
        </tbody>
    </table>
    </div>
</template>

<script>
import {mapActions} from 'vuex'
export default {
    name: 'lista-component',
    props: {
        Juegos:{
            type: Array,
            required: true,
        },
        JuegosParaVender:{
            type:Array,
        },
        totalJuegosstock:{

        }
    },
    data: function(){
        return {}
    },
    // computed: {},
    methods: {
          ...mapActions(['vender'])
    },
    // components: {},
}
</script>

<style scoped lang="scss">
.table {
    width: 50%;
    text-align: left;
    margin-left: auto;
    margin-right: auto;
    thead {
        font-weight: bold;
        font-size: 18px;
    }

}
</style>