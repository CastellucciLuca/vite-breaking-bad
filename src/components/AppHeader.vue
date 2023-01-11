<script>
import { store } from '../store.js';
import axios from 'axios';
export default {
    name: 'AppHeader',
    data() {
        return {
            store,
            apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=12&offset=0',
        }
    },
    methods: {
        getApiElement() {
            axios.get(this.apiUrl,{
                params:{
                }
            })
                .then((response) => {
                    console.log(response.data.data);
                    this.store.yuGiOhCards = response.data.data
                })
                .catch((error) => {
                    console.log(error);
                });
        }
    },
    created() {
        this.getApiElement()
    },
}
</script>

<template>
    <header>
        <div class="container-fluid">
            <h1 class="py-3">Yu-Gi-Oh</h1>
        </div>
    </header>
</template>

<style lang="scss" scoped>
</style>