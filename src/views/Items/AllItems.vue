<template>
    <v-app>
        <v-container class="container">
            <h1>Tous les items</h1>
            <div class="search">
                Rechercher un item par son nom :
                <input type="text" id="formSearchItem">
                <v-btn @click="searchItem" class="items">Search</v-btn>
            </div>
            <div class="navigation">
                <br> <br>
                Pages :
                <v-btn @click="getMyItems1" class="items">1</v-btn>
                <v-btn @click="getMyItems2" class="items">2</v-btn>
                <v-btn @click="getMyItems3" class="items">3</v-btn>
                <v-btn @click="getMyItems4" class="items">4</v-btn>
                <v-btn @click="getMyItems5" class="items">5</v-btn>
            </div>

        </v-container>
        <v-container>
            <div class="items" v-for="item in items" :key="item.id">
                <v-row>
                    <v-col>
                        <strong>{{ item.name }}</strong> <br>
                        <img  v-bind:src="item.image_url" alt="" sizes="" srcset="">

                    </v-col>
                    <!-- Affichage des objets + compétences, uniquement si valeur existante -->
                    <v-col>
                        <div v-if="item.gold_base!=null">
                            Prix = {{ item.gold_base}}
                        </div>
                        <div v-if="item.gold_base==null">
                            Spécial
                        </div>
                        <div v-if="item.flat_physical_damage_mod">
                            Dégats d'attaque : {{item.flat_physical_damage_mod}}
                        </div>
                        <div v-if="item.flat_hp_pool_mod">
                            PV : {{item.flat_hp_pool_mod}}
                        </div>
                        <div v-if="item.flat_mp_pool_mod">
                            Mana : {{item.flat_mp_pool_mod}}
                        </div>
                        <div v-if="item.flat_armor_mod">
                            Armure : {{item.flat_armor_mod}}
                        </div>
                        <div v-if="item.flat_movement_speed_mod">
                            Vitesse de déplacement : {{item.flat_movement_speed_mod}}
                        </div>
                        <div v-if="item.percent_life_steal_mod">
                            Vol de vie : {{item.percent_life_steal_mod}} %
                        </div>
                        
                        
                    </v-col>
                    <v-col>
                        <div v-if="item.flat_magic_damage_mod">
                            Puissance : {{item.flat_magic_damage_mod}}
                        </div>
                        <div v-if="item.percent_attack_speed_mod">
                            Vitesse d'attaque : {{item.percent_attack_speed_mod}} %
                        </div>
                        <div v-if="item.flat_hp_regen_mod">
                            Régéneration de base des PV : {{item.flat_hp_regen_mod}} %
                        </div>
                        <div v-if="item.flat_mp_regen_mod">
                            Régéneration de mana : {{item.flat_mp_regen_mod}} %
                        </div>
                        <div v-if="item.flat_spell_block_mod">
                            Resistance magique : {{item.flat_spell_block_mod}}
                        </div>
                        <div v-if="item.flat_crit_chance_mod">
                            Chance de coup critique : {{item.flat_crit_chance_mod}}
                        </div>
                    </v-col>
                </v-row>
            </div> 
        </v-container>
        
        <v-container>
            <div>
                Pages :
                <v-btn @click="getMyItems1" class="items">1</v-btn>
                <v-btn @click="getMyItems2" class="items">2</v-btn>
                <v-btn @click="getMyItems3" class="items">3</v-btn>
                <v-btn @click="getMyItems4" class="items">4</v-btn>
                <v-btn @click="getMyItems5" class="items">5</v-btn>
            </div>
        </v-container>    
    </v-app>
</template>

<script>
    import axios from 'axios';
    export default {

        data(){
            return {
                items:[]
            }
        },
        methods: {
            getMyItems1() {
                axios.get('https://api.pandascore.co/lol/items?page[size]50&page[number]=1&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((items) => {
                        console.log(items.request.response);
                        this.items = items.data
                    })
                    .catch(() => {
                    this.items = "Pas d'item";
                })
            },
            getMyItems2() {
                axios.get('https://api.pandascore.co/lol/items?page[size]=50&page[number]=2&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((items) => {
                        console.log(items.request.response);
                        this.items = items.data
                    })
                    .catch(() => {
                    this.items = "Pas d'item";
                })
            },
            getMyItems3() {
                axios.get('https://api.pandascore.co/lol/items?page[size]=50&page[number]=3&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((items) => {
                        console.log(items.request.response);
                        this.items = items.data
                    })
                    .catch(() => {
                    this.items = "Pas d'items";
                })
            },
            getMyItems4() {
                axios.get('https://api.pandascore.co/lol/items?page[size]=50&page[number]=4&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((items) => {
                        console.log(items.request.response);
                        this.items = items.data
                    })
                    .catch(() => {
                    this.items = "Pas d'items";
                })
            },
            getMyItems5() {
                axios.get('https://api.pandascore.co/lol/items?page[size]=50&page[number]=5&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((items) => {
                        console.log(items.request.response);
                        this.items = items.data
                    })
                    .catch(() => {
                    this.items = "Pas d'items";
                })
            },
            searchItem() {
                const search = document.getElementById("formSearchItem").value
                axios.get('https://api.pandascore.co/lol/items?search[name]='+search+'&token=YIRkECtlqBPIXmH7yaQky8SSbHO1V0ierWJyCVuipKOm_rWsqxI')
                    .then((items) => {
                        console.log(items.request.response);
                        this.items = items.data
                    })
                    .catch(() => {
                    this.items = "Pas d'items";
                })
            }           
        },
        mounted: function(){
            this.getMyItems1()
        }
    }
</script>

<style scoped>

</style>