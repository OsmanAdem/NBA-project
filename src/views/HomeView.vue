<!-- First page -->
<script setup>
    import NBAImage from '../components/NBAImage.vue'
</script>

<template>
    <NBAImage id="NBAImage" />
    <div class="input">
        <h2 class="text">Write to see teams:</h2>
        <div>
            <!-- v-model and v-on -->
            <input class="input-text" placeholder="Text" v-model="search" />
            <button class="btn" @click="fetchData">Press</button>
        </div>
        <ul>
            <!-- v-for and v-bind --->
            <li v-for="team in teams" :key="team">
                <!-- Text Interpolation -->
                {{ team.full_name }}
                <!-- v-if -->
                <div v-if="team.full_name">NBA Team</div>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                search: '',
                teams: []
            }
        },
        methods: {
            /* GET request with fetch */
            async fetchData() {
                const res = await fetch(
                    `https://www.balldontlie.io/api/v1/teams?=${this.search}`
                )
                const data = await res.json()
                this.teams = data.data
                console.log(data.data)
            }
        }
    }
</script>

<style scoped>
    /* Picture adjustments */
    #NBAImage {
        display: flex;
        height: 650px;
        width: 100%;
    }
</style>
