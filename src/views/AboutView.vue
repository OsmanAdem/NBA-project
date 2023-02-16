<script setup>
    import NBAImage2 from '../components/NBAImage2.vue'
    import NBAGames from '../components/NBAGames.vue'
</script>
<template>
    <NBAImage2 id="NBAImage2" />
    <NBAGames league="NBA" />
</template>

<style scoped>
    #NBAImage2 {
        display: flex;
        height: 700px;
        width: 100%;
    }
</style>
