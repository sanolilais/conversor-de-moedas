<template>
    <div class="conversor">
        <h2>{{moedaA}} Para {{moedaB}}</h2>
        <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA">
        <h2>{{moedaB_value}}</h2>
        <input type="button" value="Converter" v-on:click="converter">
    </div>
</template>

<script>
export default {
    name: "Conversor",
    props: ["moedaA" , "moedaB"] ,
        data() {
            return {
                moedaA_value : "" ,
                moedaB_value : 0
            };
        }, 
        methods:{
            converter() {
                let de_para = this.moedaA + "/" + this.moedaB;
                let url = "https://v6.exchangerate-api.com/v6/24a2e63f0c67ae921b870560/pair/"+de_para

                fetch(url).then(res => res.json()
                    .then(json => {
                        console.log(json)
                        let cotacao = json.conversion_rate
                        this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2)
                    }))
            }
        }
}
</script>

<style scoped>

.conversor {
    max-width: 300px;
    padding: 20px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);

}
</style>

