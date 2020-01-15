<template>
    <v-app>
        <v-container class="container">
            <h1>Tous les champions</h1>
            <div class="search">
                Rechercher un champion par son nom :
                <input type="text" id="formSearchChampion">
                <v-btn @click="searchChampion" class="Champions">Search</v-btn>
            </div>
            <div class="navigation">
                <br> <br>
                Pages :
                <v-btn @click="getMyChampions1" class="Champions">1</v-btn>
                <v-btn @click="getMyChampions2" class="Champions">2</v-btn>
                <v-btn @click="getMyChampions3" class="Champions">3</v-btn>
                <v-btn @click="getMyChampions4" class="Champions">4</v-btn>
                <v-btn @click="getMyChampions5" class="Champions">5</v-btn>
            </div>

        </v-container>
        <v-container>
            <div class="Champions" v-for="champion in champions" :key="champion.id">
                <v-row>
                    <v-col>
                        <strong>{{ champion.name }}</strong> <br>
                        <img  v-bind:src="champion.image_url" alt="" sizes="" srcset="">
                    </v-col>
                    <v-col>
                        <br>
                        HP : {{ champion.hp }} <br>
                        Magic Point (MP): {{ champion.mp }} <br>
                        Dégats par attaque : {{ champion.attackdamage }} <br>
                        Vitesse de déplacement : {{ champion.movespeed }} <br>
                        Portée d'attaque : {{ champion.attackrange }} <br>
                    </v-col>
                    <v-col>
                        <br>
                        Régénération HP : {{ champion.hpregen }} <br>
                        Régénération MP : {{ champion.mpregen }} <br>
                        Armure : {{ champion.armor }} <br>
                        Resistance magique : {{ champion.spellblock }} <br>
                    </v-col>
                </v-row>
            </div> 
        </v-container>
        
        <v-container>
            <div>
                Pages :
                <v-btn @click="getMyChampions1" class="Champions">1</v-btn>
                <v-btn @click="getMyChampions2" class="Champions">2</v-btn>
                <v-btn @click="getMyChampions3" class="Champions">3</v-btn>
                <v-btn @click="getMyChampions4" class="Champions">4</v-btn>
                <v-btn @click="getMyChampions5" class="Champions">5</v-btn>
            </div>
        </v-container>    
    </v-app>
</template>

<script>
    import axios from 'axios';
    export default {

        data(){
            return {
                champions:[]
            }
        },
        methods: {
            getMyChampions1() {
                axios.get('https://api.pandascore.co/lol/champions?page[size]=30&page[number]=1&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((champions) => {
                        console.log(champions.request.response);
                        this.champions = champions.data
                    })
                    .catch(() => {
                    this.champions = "Pas de champions";
                })
            },
            getMyChampions2() {
                axios.get('https://api.pandascore.co/lol/champions?page[size]=30&page[number]=2&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((champions) => {
                        console.log(champions.request.response);
                        this.champions = champions.data
                    })
                    .catch(() => {
                    this.champions = "Pas de champions";
                })
            },
            getMyChampions3() {
                axios.get('https://api.pandascore.co/lol/champions?page[size]=30&page[number]=3&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((champions) => {
                        console.log(champions.request.response);
                        this.champions = champions.data
                    })
                    .catch(() => {
                    this.champions = "Pas de champions";
                })
            },
            getMyChampions4() {
                axios.get('https://api.pandascore.co/lol/champions?page[size]=30&page[number]=4&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((champions) => {
                        console.log(champions.request.response);
                        this.champions = champions.data
                    })
                    .catch(() => {
                    this.champions = "Pas de champions";
                })
            },
            getMyChampions5() {
                axios.get('https://api.pandascore.co/lol/champions?page[size]=30&page[number]=5&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((champions) => {
                        console.log(champions.request.response);
                        this.champions = champions.data
                    })
                    .catch(() => {
                    this.champions = "Pas de champions";
                })
            },
            searchChampion() {
                const search = document.getElementById("formSearchChampion").value
                axios.get('https://api.pandascore.co/lol/champions?search[name]='+search+'&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((champions) => {
                        console.log(champions.request.response);
                        this.champions = champions.data
                    })
                    .catch(() => {
                    this.champions = "Pas de champions";
                })
            }           
        }
    }
</script>

<style scoped>

</style>