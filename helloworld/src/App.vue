<template>
    <div id="app">
        <h1>Com v-text</h1>
        <p v-text="msg"></p>

        <h1>Com interpolação do mustache</h1>
        <p>{{ msg }}</p>

        <p v-once v-text="msg"></p>

        <p v-if="msg.length > 0">Se vc ta vendo isso, é porque a variável msg tem length > 0</p>

        <input type="text" v-model="luego" placeholder="Contrate alguem pra Luego">
        <div v-if="luego.length > 0">
            <h1>Luego no v-for</h1>
            <ul>
                <li v-for="(employee, index) in luego"><span v-on:click="deleteEmployee(index, employee)">X</span> {{ employee }}</li>
            </ul>
            <p>De acordo com meu array, a Luego tem {{ luego.length }} funcionários.</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'app',
    data () {
        return {
            msg: 'mostrando a variável "msg"',
            luego: ['Jadher', 'Leandro', 'Jhon', 'Renato', 'Gabriel', 'Renan', 'Rodrigo', 'Carlos', 'Junior', 'André']
        }
    },
    mounted() {
        setTimeout( ()  =>  this.msg = "Eu mudei o valor de \"msg\" mas se eu usar v-once, vc nem sabe que mudou",  2000  )
    },
    methods: {
        deleteEmployee: function (index, employee){
            alert('yeah yeah, pegadinha do malandro! não vou demitir o ' + employee + ' mas se eu quisesse, o índice do array é ' + index);
        }
    }
}
</script>

<style lang="scss">
</style>
