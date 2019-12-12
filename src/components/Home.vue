<template>

    <!-- wrapper -->
    <div class="wrapper">

        <!-- section -->
        <section class="section landing home fullscreen">

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
                        <a href="portfolio.html" class="button line light">Explore More</a>
                    </div>

                </div>
                <!-- .row -->

            </div>
            <!-- .container -->

        </section>
        <!-- section -->
        <video autoplay muted loop id="myVideo">
            <source src="../assets/Storm - 16160.mp4" type="video/mp4">
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

            }
        }
    }
</script>

<style scoped>

</style>
