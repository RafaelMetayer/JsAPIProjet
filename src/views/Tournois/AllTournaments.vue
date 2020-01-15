<template>
    <v-app>
        <v-container class="container">
            <h1>Tous les tournois</h1>
            <div class="search">
                Rechercher un tournoi par son nom :
                <input type="text" id="formSearchTournament">
                <v-btn @click="searchTournament" class="tournois">Search</v-btn>
            </div>
            <div class="navigation">
                <br> <br>
                Pages :
                <v-btn @click="getMyTournaments1" class="tournois">1</v-btn>
                <v-btn @click="getMyTournaments2" class="tournois">2</v-btn>
                <v-btn @click="getMyTournaments3" class="tournois">3</v-btn>
                <v-btn @click="getMyTournaments4" class="tournois">4</v-btn>
                <v-btn @click="getMyTournaments5" class="tournois">5</v-btn>
            </div>

        </v-container>
        <v-container>
            <div class="tournois" v-for="tournoi in tournois" :key="tournoi.id">
                <v-row>
                    <v-col>
                        <strong>{{ tournoi.name }}</strong> <br>
                        <img  v-bind:src="tournoi.league.image_url" alt="" height="80" width="auto" srcset="">                        
                   </v-col>
                   <v-col>
                        Début du tournoi : {{ tournoi.begin_at }} <br>
                        <div v-if="tournoi.end_at!=null">
                            Fin du tournoi : {{ tournoi.end_at }}
                        </div>         
                   </v-col>
                   <v-col>
                        League : {{ tournoi.league.name }} <br>
                        <div v-if="tournoi.prizepool!=null">
                            Premier prix : {{ tournoi.prizepool }}
                        </div>
                        <div v-if="tournoi.winner!=null">
                            Premier prix : {{ tournoi.winner }}
                        </div>
                   </v-col>  
                </v-row>
                <v-row>
                    
                </v-row>
            </div> 
        </v-container>
        
        <v-container>
            <div>
                Pages :
                <v-btn @click="getMyTournaments1" class="tournois">1</v-btn>
                <v-btn @click="getMyTournaments2" class="tournois">2</v-btn>
                <v-btn @click="getMyTournaments3" class="tournois">3</v-btn>
                <v-btn @click="getMyTournaments4" class="tournois">4</v-btn>
                <v-btn @click="getMyTournaments5" class="tournois">5</v-btn>
            </div>
        </v-container>    
    </v-app>
</template>

<script>
    import axios from 'axios';
    export default {

        data(){
            return {
                tournois:[]
            }
        },
        methods: {
            getMyTournaments1() {
                axios.get('https://api.pandascore.co/lol/tournaments?page[size]=30&page[number]=1&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((tournois) => {
                        console.log(tournois.request.response);
                        this.tournois = tournois.data
                    })
                    .catch(() => {
                    this.tournois = "Pas de tournoi";
                })
            },
            getMyTournaments2() {
                axios.get('https://api.pandascore.co/lol/tournaments?page[size]=30&page[number]=2&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((tournois) => {
                        console.log(tournois.request.response);
                        this.tournois = tournois.data
                    })
                    .catch(() => {
                    this.tournois = "Pas de tournoi";
                })
            },
            getMyTournaments3() {
                axios.get('https://api.pandascore.co/lol/tournaments?page[size]=30&page[number]=3&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((tournois) => {
                        console.log(tournois.request.response);
                        this.tournois = tournois.data
                    })
                    .catch(() => {
                    this.tournois = "Pas de tournoi";
                })
            },
            getMyTournaments4() {
                axios.get('https://api.pandascore.co/lol/tournaments?page[size]=30&page[number]=4&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((tournois) => {
                        console.log(tournois.request.response);
                        this.tournois = tournois.data
                    })
                    .catch(() => {
                    this.tournois = "Pas de tournoi";
                })
            },
            getMyTournaments5() {
                axios.get('https://api.pandascore.co/lol/tournaments?page[size]=30&page[number]=5&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((tournois) => {
                        console.log(tournois.request.response);
                        this.tournois = tournois.data
                    })
                    .catch(() => {
                    this.tournois = "Pas de tournoi";
                })
            },
            searchTournament() {
                const search = document.getElementById("formSearchTournament").value
                axios.get('https://api.pandascore.co/lol/tournaments?search[name]='+search+'&page[size]=100&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((tournois) => {
                        console.log(tournois.request.response);
                        this.tournois = tournois.data
                    })
                    .catch(() => {
                    this.tournois = "Pas de tournoi";
                })
            }           
        }
    }
</script>

<style scoped>

</style>