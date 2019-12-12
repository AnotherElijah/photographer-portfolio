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
                                <li data-album="black-white"><button :click="()=>this.switchSection(1)">Black & White</button></li>
                                <li data-album="darker-than-black"><button :click="()=>this.switchSection(2)">Darker Than Black</button></li>
                                <li data-album="madness"><span>Madness</span></li>
                                <li data-album="shades"><span>Shades</span></li>
                                <li data-album="sleeping-beauty"><span>Sleeping Beauty</span></li>
                            </ul>
                        </div>
                        <!-- .content -->
                    </div>
                    <!-- .albums -->
                </div>
                <!-- .row -->

                <!-- .row -->
                <div class="grid row">
                    <GallerySection v-if="this.currentSection===1" :current-section="this.currentSection"></GallerySection>
                    <GallerySection v-if="this.currentSection===2" :current-section="this.currentSection"></GallerySection>
                </div>
                <!-- .row -->

            </div>
            <!-- .container -->

        </section>
        <!-- section -->

    </div>
</template>
<script>
    import GallerySection from "@/components/gallery/Gallery-section";
    export default {
        name: "Portfolio",
        components: {GallerySection},
        created(){

        },
        data: function(){
          return {
              currentSection: 1
          }
        },
        methods:{
            switchSection: function(section = 1){
                console.log('***')
                this.currentSection = section;
            }
        }
    }
</script>
<style scoped>

</style>
