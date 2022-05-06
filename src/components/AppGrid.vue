<template>
    <section class="container">
        <!-- 
            gender: "Male"
            id: 1
            image: "https://rickandmortyapi.com/api/character/avatar/1.jpeg"
            name: "Rick Sanchez"
            origin: "Earth (C-137)"
            species: "Human"
            status: "Alive"
            type: "Human"
         -->
        <app-loader v-if="loading" />
        <div class="row">
            <div v-for="character in characterList" :key="character.id" class="col-6 col-md-4 col-lg-3 gy-3">
                <app-card :item="character"/>
            </div>
        </div>
        <app-footer :len="characterList.length" v-if="!loading"/>
    </section>
</template>

<script>
    import AppLoader from './AppLoader.vue'
    import AppCard from './AppCard.vue'
    import AppFooter from './AppFooter.vue'
    import axios from 'axios'

    export default {
        name: 'AppGrid',
        components: {
            AppLoader,
            AppCard,
            AppFooter
        },
        data() {
            return {
                characterList: [],
                endPoint: 'https://api.sampleapis.com/rickandmorty/',
                loading: false
            }
        },
        mounted() {
            this.loading = true;
            axios.get(`${this.endPoint}characters`).then((res) => {
                this.characterList = res.data
                this.loading = false;
            }).catch((error) => {
                console.log(error)
                this.loading = false;
            })
        }
    }
</script>

<style lang="scss" scoped>

</style>