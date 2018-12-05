<template>
    <div class="container">
        <h1>Registrar item</h1>
        <br>
        <div class="columns">
            <div class="column">
                <div class="field">
                    <label class="label">Nombre</label>
                    <div class="control">
                        <input class="input" type="text" placeholder="Nombre del item" v-model="item.nombre">
                    </div>
                </div>

                <div class="field">
                    <label class="label">Precio</label>
                    <div class="control">
                        <input class="input" type="number" placeholder="precio del item" v-model="item.precio">
                    </div>
                </div>

                <div class="field">
                    <label class="label">stock</label>
                    <div class="control">
                        <input class="input" type="number" placeholder="stock del item" v-model="item.stock">
                    </div>
                </div>
                <a @click="registrar" class="button is-primary">Registrar</a>
            </div>
        </div>
    </div>
</template>
<script>
const axios = require('axios');
export default {
    name:"principal",
    data(){
        return{
            item:{
                nombre:'',
                precio:0,
                stock:0
            }
        }
    },
    methods:{
        registrar(){
        let puerto1 = '3000'
        let puerto2 = '4000'
        axios.post(`http://localhost:${puerto1}/registrar/`,this.item).then((response) => {
          console.log(response.data)
        })
        this.axios.post(`http://localhost:${puerto2}/registrar/`,this.item).then((response) => {
          console.log(response.data)
        })
        }
    }
}
</script>
