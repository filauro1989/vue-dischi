<template>
    <div class="container-fluid bg-color">
        <img src="../assets/spotify-logo.png" alt="">
    </div>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            
        }
    },
}
</script>

<style lang="scss" scoped>
    @import "../assets/scss/partials/_variables.scss";
    @import "../assets/scss/partials/_commons.scss"; 


.bg-color {
    background-color: $cardBackground;
}
.container-fluid {
    img {
        height: 50px;
        margin: 0.7em 0;
        margin-left: 1.8em;
    }
}

</style>