<template>
        <div class="container-fluid bg-color" >
            <div class="w-60 centered pt-6">
                <div class="row row-cols-5">
                    <div class="col text-center text-light px-3">
                        <div class="card-wrapper card-bg-color p-3">
                            <img src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
                            <h4>NEW JERSEY</h4>
                            <h5>Bon Jovi</h5>
                            <h6>1988</h6>
                        </div>
                    </div>
                </div>
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
            .card-bg-color {
                background-color: $cardBackground;
            }
    };
    .container-fluid {
        height: calc(100vh - 50px - 1.4em);
        width: 100vw;
    };
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