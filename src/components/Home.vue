<template>

    <!-- wrapper -->
    <div class="">

        <!-- section -->
        <section :class="window.width<901?'section landing home fullscreen background':'section landing home fullscreen'">

            <!-- .background -->
            <div class="background video" data-type="video" data-url="./images/home/video/background.mp4" data-poster="./images/home/video/background.jpg"></div>
            <!-- .background -->

            <div class="border"></div>

            <!-- .container -->
            <div class="container vertical-center u-inline-block">

                <!-- .row -->
                <div class="row animated">

                    <div class="home-container main item twelve columns">
                        <span class="text margin-bot--15">marilyn black photography</span>
                        <h1 class="title title-very-large u-font-light margin-bot--25">brilliant measures</h1>
                        <a href="portfolio" class="button line light">Explore More</a>
                    </div>

                </div>
                <!-- .row -->

            </div>
            <!-- .container -->

        </section>
        <!-- section -->
        <video v-if="window.width>900" autoplay muted loop id="myVideo" width="100%">
            <source src="../assets/bg-tree.mp4" type="video/mp4">
        </video>
    </div>

    <!-- .wrapper -->
</template>

<script>
    export default {
        name: "Home",
        props: ['active'],
        data(){
            return {
                window: {
                    width: 0,
                    height: 0
                }
            }
        },
        created() {
            window.addEventListener('resize', this.handleResize);
            this.handleResize();
        },
        destroyed() {
            window.removeEventListener('resize', this.handleResize)
        },
        methods: {
            handleResize() {
                this.window.width = window.innerWidth;
                this.window.height = window.innerHeight;
            }
        }
    }
</script>

<style scoped>
    section.home.fullscreen.background{
        background-image: url(../assets/forest-1031022_1920.jpg);
        background-size: cover;
        height: 100vh;
    }

    @media (max-width: 768px){
        span.text{
            font-size: 60%;
        }
        h1.title {
            font-size: 304%!important;
        }
        a.button{
            /*width: 33%;*/
            font-size: 50%;
            border-bottom-width: 1px;
            border-top-width: 1px;
        }
    }

</style>
