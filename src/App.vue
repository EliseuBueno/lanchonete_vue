<template>
    <NavBar/>    
    <router-view/>
    <Footer/>
</template>

<script>
import NavBar from './components/layouts/NavBar.vue';
import Footer from './components/layouts/Footer.vue';
export default {
    name: "App",
    components: {
        NavBar, Footer
    }
}
</script>
<style>

</style>
