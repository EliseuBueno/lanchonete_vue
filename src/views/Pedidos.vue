<template>
    <div class="container"><br>
        <h1>Gerenciar Pedidos:</h1><br>
        <Dashboard/><br>
    </div>
</template>

<script>
import Dashboard from '@/components/Dashboard.vue';
export default {
    name: "Pedidos",
    components: { Dashboard }
}
</script>