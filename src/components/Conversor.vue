<template>
    <div class="conversor">
        <h2>{{moedaA}} Para {{moedaB}}</h2>
        <div class="painel-convert">
            <input type="text" class="input-convert" v-model="moedaA_value" v-bind:placeholder="moedaA">
            <button class="btn-convert" v-on:click="converter">Converter <i class="fa-solid fa-arrow-right-arrow-left"></i></button>
            </div>
            <h2>{{moedaB_value}}</h2>
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
                let url = `${process.env.VUE_APP_BASE_URL}/${process.env.VUE_APP_API_KEY}/pair/${de_para}`

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
    padding: 25px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    width: 300px;
}

.painel-convert {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.btn-convert {
    background-color: #2EA62C;
    width: 150px;
    height: 50px;
    border-radius: 7px;
    cursor: pointer;
    color: #fff;
    font-weight: 700;
}

.input-convert {
    height: 38px;
    width: 240px;
    margin: 20px;
    font-size: 16px;
    font-weight: 700;

    
}

</style>

