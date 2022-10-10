<template>
    <NavBar :logo="logo_src" :alt="app_name"/> 
    <router-view/>
    <Footer/>
</template>

<script>
import NavBar from './components/layouts/NavBar.vue';
import Footer from './components/layouts/Footer.vue';
export default {
    name: "App",
    components: {
    NavBar,
    Footer
},
    data() {
        return {
            logo_src: '/img/logo.png',
            app_name: 'Make Your Burger',
        }
    }
}
</script>
<style>

</style>
