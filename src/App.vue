<template>
    <div id="app">
        <h1>Star Team</h1>
        <h3>View the characters and planets from Star Wars!</h3>
        <h4>
            <router-link to="/data/people" class="link">Meet the Characters</router-link> |
            <router-link to="/data/planets" class="link">Explore the Planets</router-link>
        </h4>
        <router-view></router-view>
    </div>
</template>