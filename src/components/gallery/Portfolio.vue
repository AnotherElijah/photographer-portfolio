<template>
    <div class="wrapper">
        <!-- section -->
        <section class="section portfolio filterbar">

            <!-- .container -->
            <div class="container offset offset-top--0">

                <!-- header -->
                <header class="animated">
                    <!-- .content -->
                    <div class="content">
                        <span class="text">Long Live Clean</span>
                        <h2 class="headline title">Marvelous Work</h2>
                        <div class="devider"></div>
                    </div>
                    <!-- .content -->
                </header>
                <!-- header -->

                <!-- .row -->
                <div class="filter row animated">
                    <!-- .albums -->
                    <div class="albums">
                        <!-- .content -->
                        <div class="content">
                            <ul>
                                <!--??????????????????????-->
                                <li data-album="black-white"><span v-on:click="switchSection(1)">Black & White</span></li>
                                <li data-album="darker-than-black"><span v-on:click="switchSection(2)">Darker Than
                                    Black</span>
                                </li>
                                <li data-album="madness" v-on:click="switchSection(3)"><span>Madness</span></li>
                                <li data-album="shades" v-on:click="switchSection(4)"><span>Shades</span></li>
                                <li data-album="sleeping-beauty" v-on:click="switchSection(5)"><span>Sleeping Beauty</span></li>
                            </ul>
                        </div>
                    </div>
                </div>

                <div class="grid row">
                    <div>
                        <Gallery-section v-if="this.currentSection===1"
                                         :current-section="1"></Gallery-section>
                    </div>
                    <br>
                    <div>
                        <Gallery-section v-if="this.currentSection===2"
                                         :current-section="2"></Gallery-section>
                    </div>
                    <div>
                        <Gallery-section v-if="this.currentSection===3"
                                         :current-section="3"></Gallery-section>
                    </div>
                    <div>
                        <Gallery-section v-if="this.currentSection===4"
                                         :current-section="4"></Gallery-section>
                    </div>
                    <div>
                    <Gallery-section v-if="this.currentSection===5"
                                     :current-section="5"></Gallery-section>
                </div>
                </div>
            </div>
        </section>
    </div>
</template>
<script>
    import GallerySection from "@/components/gallery/Gallery-section";

    export default {
        name: "Portfolio",
        components: {GallerySection},
        created() {

        },
        data() {
            return {
                section: 1
            }
        },
        computed: {
            currentSection:
                {
                    set: function (section) {
                        return this.section = section;
                    },
                    get: function () {
                        return this.section
                    }
                }
        },
        methods: {
            switchSection(section) {
                this.currentSection = section;
            }
        }
    }
</script>
<style scoped>

</style>
