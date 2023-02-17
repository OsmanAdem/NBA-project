<template>
    <div class="NBAGames">
        <!-- Text Interpolation -->
        <h1>Welcome to the {{ league }}!</h1>
    </div>
</template>

<script>
    /* props */
    export default {
        props: ['league']
    }
</script>
