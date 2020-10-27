<template>
    <div class="ui secondary pointing menu">
        <router-link to="/" class="active item"> Image Storage</router-link>

        <div class="right menu">

            <div class='horizontal' v-if="isLoggedIn">
               <router-link to="/" href="" class="item">Gallery</router-link>
               <router-link to="/upload" href="" class="item">Upload</router-link>
               <a href="" class="item" @click="logout">LogOut</a>
            </div>



            <a v-else href="#" class="ui item" @click="login">Login</a>
        </div>
    </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex';
export default {
    name: 'AppHeader',
    methods: mapActions(['login', 'logout']),
    computed: mapGetters(['isLoggedIn'])
}
</script>

<style scoped>
    .horizontal {
        display: flex;
        flex-direction: row;
    }
</style>