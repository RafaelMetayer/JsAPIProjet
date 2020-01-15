<template>
    <v-app>
        <v-container class="container">
            <h1>Toutes les équipes</h1>
            <div class="search">
                Rechercher une équipe par son nom :
                <input type="text" id="formSearchTeam">
                <v-btn @click="searchTeam" class="teams">Search</v-btn>
            </div>
            <div class="navigation">
                <br> <br>
                Pages :
                <v-btn @click="getMyTeams1" class="teams">1</v-btn>
                <v-btn @click="getMyTeams2" class="teams">2</v-btn>
                <v-btn @click="getMyTeams3" class="teams">3</v-btn>
                <v-btn @click="getMyTeams4" class="teams">4</v-btn>
                <v-btn @click="getMyTeams5" class="teams">5</v-btn>
                <v-btn @click="getMyTeams6" class="teams">6</v-btn>
                <v-btn @click="getMyTeams7" class="teams">7</v-btn>
                <v-btn @click="getMyTeams8" class="teams">8</v-btn>
            </div>

        </v-container>
        <v-container>
            <div class="teams" v-for="team in teams" :key="team.id">
                <v-row>
                    <v-col>
                        <strong>{{ team.name }}</strong> <br>
                        <img  v-bind:src="team.image_url" alt="" height="80" width="auto" srcset="">
                    </v-col>
                    <v-col>
                        <br>
                        Acronyme : {{ team.acronym }} <br>
                        Jeux joués : {{ team.current_videogame.name }}
                    </v-col>
                    <v-col>
                        <div class="teams" v-for="player in team.players" :key="player.id">
                            Joueurs : {{ player.name }} <br>
                        </div>
                    </v-col>
                    <v-col>
                        <div class="teams" v-for="player in team.players" :key="player.id">
                            <div v-if="player.role!=null">
                                Role : {{ player.role}} <br>
                            </div>
                        </div>
                    </v-col>
                </v-row>
            </div> 
        </v-container>
        
        <v-container>
            <div>
                Pages :
                <v-btn @click="getMyTeams1" class="teams">1</v-btn>
                <v-btn @click="getMyTeams2" class="teams">2</v-btn>
                <v-btn @click="getMyTeams3" class="teams">3</v-btn>
                <v-btn @click="getMyTeams4" class="teams">4</v-btn>
                <v-btn @click="getMyTeams5" class="teams">5</v-btn>
                <v-btn @click="getMyTeams6" class="teams">6</v-btn>
                <v-btn @click="getMyTeams7" class="teams">7</v-btn>
                <v-btn @click="getMyTeams8" class="teams">8</v-btn>
            </div>
        </v-container>    
    </v-app>
</template>

<script>
    import axios from 'axios';
    export default {

        data(){
            return {
                teams:[],
                players:[]
            }
        },
        methods: {
            getMyTeams1() {
                axios.get('https://api.pandascore.co/lol/teams?page[size]=100&page[number]=1&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((teams) => {
                        console.log(teams.request.response);
                        this.teams = teams.data
                    })
                    .catch(() => {
                    this.teams = "Pas d'équipe";
                })
            },
            getMyTeams2() {
                axios.get('https://api.pandascore.co/lol/teams?page[size]=100&page[number]=2&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((teams) => {
                        console.log(teams.request.response);
                        this.teams = teams.data
                    })
                    .catch(() => {
                    this.teams = "Pas d'équipe";
                })
            },
            getMyTeams3() {
                axios.get('https://api.pandascore.co/lol/teams?page[size]=100&page[number]=3&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((teams) => {
                        console.log(teams.request.response);
                        this.teams = teams.data
                    })
                    .catch(() => {
                    this.teams = "Pas d'équipe";
                })
            },
            getMyTeams4() {
                axios.get('https://api.pandascore.co/lol/teams?page[size]=100&page[number]=4&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((teams) => {
                        console.log(teams.request.response);
                        this.teams = teams.data
                    })
                    .catch(() => {
                    this.teams = "Pas d'équipe";
                })
            },
            getMyTeams5() {
                axios.get('https://api.pandascore.co/lol/teams?page[size]=100&page[number]=5&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((teams) => {
                        console.log(teams.request.response);
                        this.teams = teams.data
                    })
                    .catch(() => {
                    this.teams = "Pas d'équipe";
                })
            },
            getMyTeams6() {
                axios.get('https://api.pandascore.co/lol/teams?page[size]=100&page[number]=6&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((teams) => {
                        console.log(teams.request.response);
                        this.teams = teams.data
                    })
                    .catch(() => {
                    this.teams = "Pas d'équipe";
                })
            },
            getMyTeams7() {
                axios.get('https://api.pandascore.co/lol/teams?page[size]=100&page[number]=7&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((teams) => {
                        console.log(teams.request.response);
                        this.teams = teams.data
                    })
                    .catch(() => {
                    this.teams = "Pas d'équipe";
                })
            },
            getMyTeams8() {
                axios.get('https://api.pandascore.co/lol/teams?page[size]=100&page[number]=8&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((teams) => {
                        console.log(teams.request.response);
                        this.teams = teams.data
                    })
                    .catch(() => {
                    this.teams = "Pas d'équipe";
                })
            },
            searchTeam() {
                const search = document.getElementById("formSearchTeam").value
                axios.get('https://api.pandascore.co/lol/teams?search[name]='+search+'&page[size]=100&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((teams) => {
                        console.log(teams.request.response);
                        this.teams = teams.data
                    })
                    .catch(() => {
                    this.teams = "Pas d'équipe";
                })
            }
        },
        mounted: function(){
            this.getMyTeams1()
        }
    }
</script>

<style scoped>

</style>