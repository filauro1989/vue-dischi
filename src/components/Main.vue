<template>
        <div class="container bg-color" >
            <div class="w-60 centered">
                asd
            </div>
        </div>
</template>

<script>
export default {
    name: 'Main',
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
        background-color: $backgroundColor;
    };
    .container {
        height: calc(100vh - 50px - 1.65em);
        width: 100vw;
    }
</style>