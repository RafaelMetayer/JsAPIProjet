<template>
    <v-app>
        <v-container>
            <h1>Tous les champions</h1>
            <v-btn @click="getMyChampions">TEST</v-btn>
        </v-container>
        <div>
            <div class="TEST" v-for="champion in champions" :key="champion.id">
                <v-row>
                    <v-col>
                        <strong>{{ champion.name }}</strong> <br>
                        <img src="" alt="" sizes="" srcset="">
                    </v-col>
                    <v-col>
                        HP : {{ champion.hp }} <br>
                        Magic Point (MP): {{ champion.mp }} <br>
                        Dégats par attaque : {{ champion.attackdamage }} <br>
                        Vitesse de déplacement : {{ champion.movespeed }} <br>
                        Portée d'attaque : {{ champion.attackrange }} <br>
                    </v-col>
                    <v-col>
                        Régénération HP : {{ champion.hpregen }} <br>
                        Régénération MP : {{ champion.mpregen }} <br>
                        Armure : {{ champion.armor }} <br>
                        Resistance magique : {{ champion.spellblock }} <br>
                    </v-col>
                </v-row>
            </div> 
        </div>   
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
            getMyChampions() {
                axios.get('https://api.pandascore.co/lol/champions?page[size]=&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
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