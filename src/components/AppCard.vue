<template>
            <!--gender: "Male"
            id: 1
            image: "https://rickandmortyapi.com/api/character/avatar/1.jpeg"
            name: "Rick Sanchez"
            origin: "Earth (C-137)"
            species: "Human"
            status: "Alive"
            type: "Human" -->
    <div class="text-center">
        <img :src="item.image" :alt="item.name">
        <h4 class="mt-3">{{item.name}}</h4>
        <div>{{item.origin}}</div>
        <div class="fw-bold">{{item.species}}</div>
    </div>
</template>

<script>
export default {
    name: 'AppCard',
    props: {
        item: Object
    }  
}
</script>

<style lang="scss" scoped>
    @import '@/style/variables.scss';

    h4{
        text-transform: uppercase;

        &:after{
            content: '';
            display: block;
            width: 50px;
            height: 3px;
            margin: 1rem auto;
            background: currentColor;
        }
    }

    img{
        border-radius: 50%;
        box-shadow: 0 0 6px 3px rgba(#000, 0.15);
        width: 100%;
    }
</style>