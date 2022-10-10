<template>
    <Carousel 
        :img_01="img_carousel_01" 
        :img_02="img_carousel_02" 
        :img_03="img_carousel_03" 
        :alt_01="alt_carousel_01"
        :alt_02="alt_carousel_02"
        :alt_03="alt_carousel_03"    
    /><br>
    <div class="container">
        <h1 class="text-center">Conteúdo da Home</h1><br>
        <BtnCadastrar/><br>
        <FormBurger/>
    </div><br>
</template>

<script>
import Carousel from '@/components/layouts/Carousel.vue'
import BtnCadastrar from '@/components/buttons/BtnCadastrar.vue'
import FormBurger from '@/components/forms/FormBurger.vue';

export default {
    name: "Home",
    components: { Carousel, BtnCadastrar, FormBurger },
    data() {
        return {
            'img_carousel_01': '/img/alto.jpg',
            'img_carousel_02': '/img/camera.jpg',
            'img_carousel_03': '/img/pes.jpg',
            'alt_carousel_01': 'Imagem 1',
            'alt_carousel_02': 'Imagem 2',
            'alt_carousel_03': 'Imagem 3'
        }
    }
}
</script>

<script>

</script>
