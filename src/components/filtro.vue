<template>
<div>

    <h4> <label>Seleccione código de juego</label>
        <input type="text" v-model="search" @change="buscar">
    </h4>

    <h4> Cantidad de juegos disponibles: {{totalJuegosstock}}</h4>

    <table class="table">
        <thead>
            <tr>
                <th>Código</th>
                <th>Nombre</th>
                <th>Stock</th>
                <th>Precio</th>

            </tr>
        </thead>
        <tbody>
            <tr v-for="juego in Juegos" :key="juego.codigo" :style="{background:juego.color,color:juego.font}">
                <th>{{juego.codigo}}</th>
                <td>{{juego.nombre}}</td>
                <td>{{juego.stock}}</td>
                <td>{{juego.precio}}</td>

            </tr>
        </tbody>
    </table>

</div>
</template>

<script>
export default {
    name: "filtro",
    props: {
        Juegos: {
            type: Array,
            required: true,
        },
        totalJuegosstock: {},
    },
    data: function () {
        return {
            search: "",
        };
    },
    // computed: {},
    methods: {
        buscar() {
            this.$emit("buscar", {
                search_codigo: this.search,
            });
        },
    },
    components: {},
};
</script>

<style lang="scss" scoped>
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
