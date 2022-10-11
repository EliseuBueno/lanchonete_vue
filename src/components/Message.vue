<template>
    <div class="alert alert-primary" role="alert">
        <p>{{msg}}</p>
    </div>
</template>

<script>
export default {
    name: 'Message',
    props: {
        msg: String
    }
}
</script>