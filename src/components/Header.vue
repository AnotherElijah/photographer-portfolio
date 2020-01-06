<template>
    <div>
    <!-- header -->
    <Menu v-bind:active="state.open"></Menu>
    <header class="header animated">
        <!-- .container -->
        <div class="container">

            <!-- .row -->
            <div class="row header-wrapper">

                <!-- .item -->
                <div class="item one-half column">

                    <!-- logo -->
                    <div class="logo">
                        <a href="/">
                            <img src="../assets/images/logo/logo-light.png" alt="">
                        </a>
                    </div>
                    <!-- logo -->

                </div>
                <!-- .item -->

                <!-- .item -->
                <div class="item one-half column">

                    <!-- Menu -->
                    <div :class="state.open? 'menu light menu-x':'menu light'">
                        <div class="select-menu" v-on:click="clickHandler()"></div>
                    </div>
                    <!-- Menu -->

                </div>
                <!-- .item -->

            </div>
            <!-- .row -->

        </div>
        <!-- .container -->

    </header>
    <!-- header -->
    </div>
</template>

<script>
    import Menu from "@/components/Menu";
    export default {
        name: "Header",
        components: {Menu},
        data(){
            return {
                state: {
                    open: false
                }
            }
        },
        methods: {
            clickHandler: function () {
                this.state.open = !this.state.open;
            }
        },
        created() {
        }

    }
</script>

<style scoped>
    .header-wrapper{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }
    .header-wrapper .one-half{
        width: auto;
    }
    @media (max-width: 600px){
        .header.animated{
            padding-top: 50px;
        }
    }
</style>
