<script>
import { store } from '../store.js';
import axios from 'axios';
export default {
    name: 'AppHeader',
    data() {
        return {
            store,
            apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0',
        }
    },
    methods: {
        getApiElement() {
            axios.get(this.apiUrl, {
                params: {
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
            <div class="container-fluid">
                <div class="row">
                    <div class="col-12 d-flex">
                        <img src="../assets/Yu-Gi-Oh!_(Logo).jpg" alt="yugioh-logo">
                        <h1 class="py-3">Yu-Gi-Oh Api</h1>
                    </div>
                </div>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
img {
    width: 150px;
    object-fit: contain;
}
</style>