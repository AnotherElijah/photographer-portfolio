<template>

    <!-- wrapper -->
    <div class="">

        <!-- section -->
        <section
                :class="window.width<901?'section landing home fullscreen background':'section landing home fullscreen'">

            <!-- .background -->
            <div class="background video" data-type="video" data-url="./images/home/video/background.mp4"
                 data-poster="./images/home/video/background.jpg"></div>
            <!-- .background -->

            <div class="border"></div>

            <!-- .container -->
            <div class="container vertical-center u-inline-block bg-circle">

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
        <div class="video-wrapper">
            <video v-if="window.width>900" autoplay muted loop id="myVideo">
                <source src="../assets/bg-tree.mp4" type="video/mp4">
            </video>
        </div>
    </div>

    <!-- .wrapper -->
</template>

<script>
    export default {
        name: "Home",
        props: ['active'],
        data() {
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
    .video-wrapper{
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        z-index: -1;
        background-color: #242d2b;
    }
    video {
        height: 112vh;
        width: auto;
        z-index: -1;
        position: relative;
    }

    section.home.fullscreen.background {
        background-image: url(../assets/forest-1031022_1920.jpg);
        background-size: cover;
        height: 100vh;
    }

    .section.landing.home.fullscreen {
        height: 100vh;
    }

    .bg-circle {
        background: radial-gradient(circle, rgba(2, 0, 36, 0) 0%, rgba(37, 22, 22, 0.34217436974789917) 35%, rgba(0, 212, 255, 0) 35.1%);
        background-size: 1669px;
        background-repeat: no-repeat;
        background-position: 50% 50%
    }

    @media (max-height: 860px) {
        .bg-circle {
            background: radial-gradient(circle, rgba(2, 0, 36, 0) 0%, rgba(37, 22, 22, 0.34217436974789917) 22%, rgba(0, 212, 255, 0) 39.1%);
            background-size: 1038px;
            background-position: center;
        }
    }

    @media (max-width: 768px) {
        .bg-circle {
            background: unset;
            background-repeat: no-repeat;
            background-position: 50% 50%
        }

        span.text {
            font-size: 60%;
        }

        h1.title {
            font-size: 304% !important;
        }

        a.button {
            /*width: 33%;*/
            font-size: 50%;
            border-bottom-width: 1px;
            border-top-width: 1px;
        }
    }

</style>
