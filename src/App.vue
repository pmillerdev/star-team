<template>
    <div id="app">
        <h1>{{title}}</h1>
        <h3>{{subtitle}}</h3>
        <div class="container-fluid">
            <div class="row">
                <Character v-for="(id, index) in initial_ids" :key="index" :id="id" />
            </div>
        </div>
    </div>
</template>

<script>
import Character from "./components/Character.vue"

export default {
    name: 'app',
    data() {
        return {
            title: 'Star Team',
            subtitle: 'Generate your dream team of star wars characters!',
            initial_ids: [1, 13, 20]
        }
    },
    components: {
        Character
    }
}
</script>