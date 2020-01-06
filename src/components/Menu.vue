<template>
    <!-- nav -->
    <nav :class="active?'navigation active':'navigation'">

        <!-- .container -->
        <div class="container fullscreen menu-container menu-wrapper">

            <!-- .row -->
            <div class="header row" style="padding: 12vh;">

                <!-- .item -->
                <div class="item one-half column">
                    <!-- logo -->
                    <div class="logo">
                        <a href="/">
                            <img src="assets/images/logo/logo-light.png" alt="">
                        </a>
                    </div>
                    <!-- logo -->
                </div>
                <!-- .item -->

            </div>
            <!-- .row -->

            <!-- .row -->
            <div class="menu row">

                <ul>
                    <li class="active">
                        <a href="/"><h2>Home</h2></a>
                    </li>
                    <li>
                        <a href="portfolio"><h2>Portfolio</h2></a>
                    </li>
                    <li>
                        <a href="about"><h2>About</h2></a>
                    </li>
                    <li>
                        <a href="contact"><h2>Contact</h2></a>
                    </li>
                </ul>

            </div>
            <!-- .row -->

            <!-- .row -->
            <div class="links row">

                <!-- .row -->
                <div class="social-links row">
                    <ul>
                        <li>
                            <a href="http://facebook.com" class="button icon social-facebook light" target="_blank"></a>
                        </li>
                        <li>
                            <a href="http://twitter.com" class="button icon social-twitter light" target="_blank"></a>
                        </li>
                        <li>
                            <a href="http://instagram.com" class="button icon social-instagram light" target="_blank"></a>
                        </li>
                    </ul>
                </div>
                <!-- .row -->

                <!-- .row -->
                <div class="copyrights row">
                    <h6>© 2019 Turin. All Rights Reserved. made by <a href="#" target="_blank">Royalz Store</a>.</h6>
                </div>
                <!-- .row -->

            </div>
            <!-- .row -->

        </div>
        <!-- .container -->

    </nav>
    <!-- nav -->
</template>

<script>
    export default {
        name: "Menu",
        props: ['active'],
        created() {
        }
    }
</script>

<style scoped>
    .menu-wrapper{
        min-height: 568px;
    }
</style>
