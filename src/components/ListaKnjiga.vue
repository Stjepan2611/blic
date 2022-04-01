<template>
    <div>
        <h1>Lista knjiga</h1>
        <table border="1px">
            <tr>
                 <td>Naziv</td>
                 <td>Autor</td>
                 <td>Datum izdanja</td>
            </tr>
        </table>
    </div>
</template>

<script>
import Vue from 'vue';
import axios from 'axios'
import VueAxios from 'vue-axios'
Vue.use(VueAxios.axios)
export default {
    name:"ListaKnjiga",
    data()
    {
        return{list:undefined}
    },
    mounted(){
        Vue.axios.get('https://www.anapioficeandfire.com/api/books')
        .then((resp)=>{
            this.list=resp.data.data;
            console.warn(resp.data.data)
        })

    }
}
</script>
