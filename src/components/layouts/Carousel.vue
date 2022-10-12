<template>

    <div id="carouselExampleControls" class="carousel slide" data-bs-ride="carousel">
        <div class="carousel-inner carousel">
            <div class="carousel-item active">
                <img :src="img_01" class="d-block w-100" :alt="alt_01">
            </div>
            <div class="carousel-item">
                <img :src="img_02" class="d-block w-100" :alt="alt_02">
            </div>
            <div class="carousel-item">
                <img :src="img_03" class="d-block w-100" :alt="alt_03">
            </div>
        </div>
        <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="prev">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Previous</span>
        </button>
        <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="next">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
        </button>
    </div>
</template>

<script>
    export default {
        name: 'Carousel',
        data() {
            return {
                
            }
        },
        props: [
            'img_01',
            'img_02',
            'img_03',
            'alt_01',
            'alt_02',
            'alt_03',    
        ]
    }
</script>

<style>
    .carousel{
        height: 500px;
    }
</style>