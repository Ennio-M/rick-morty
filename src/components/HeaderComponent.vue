<template>
    <header>
        <h1 class="text-center my-5">{{msg}}</h1>
    </header>
</template>

<script>
export default {
    name: 'HeaderComponent',
    props: ['msg']
}
</script>

<style lang="scss" scoped>
    header{
        h1{
            font-weight: 700;
        }
    }
</style>