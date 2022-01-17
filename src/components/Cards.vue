<template>
    <div class="col text-center text-light px-3">
        <div class="card-wrapper card-bg-color p-3">
            <img :src="image" alt="">
            <h4>{{ title }}</h4>
            <h5>{{ author }}</h5>
            <h6>{{ year }}</h6>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Cards',
    data() {
        return {
            
        }
    },
    props: [
        'image',
        'title',
        'author',
        'genre',
        'year'
    ]
}
</script>

<style lang="scss">

    @import "../assets/scss/partials/_variables.scss";
    .card-bg-color {
                background-color: $cardBackground;
            }
    .col {
        h4 {
            padding-top: 0.5em
        };
        h5 {
            color: $textLight;
            margin-top: 1em
        };
        h6 {
            color: $textLight;
        };
        img {
            width: 100%;
        }
    }
</style>