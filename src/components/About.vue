<template>
    <!-- wrapper -->
    <div class="wrapper">

        <!-- section -->
        <section :class="state.urlChange?'section page about slide-up':'section page about'">

            <!-- .container -->
            <div class="container">

                <div class="row">

                    <div class="cover fullscreen one-half column height-100">

                        <div class="background image fill" data-url="../assets/man-3337204_1920.jpg"></div>

                    </div>

                    <div class="content one-half column">

                        <span class="margined">About Me</span>

                        <h2 class="title">“What i’m trying to focus on in my work is to capture the perfect”</h2>

                        <div class="devider margined"></div>

                        <p class="text">Donec vulputate sit amet elit at posuere. Nulla facilisi. Sed congue, orci in porttitor vestibulum, arcu ligula accumsan sem, ac rutrum dui enim sodales diam. Phasellus id orci et mauris pellentesque laoreet ac posuere velit.</p>

                        <a v-on:click="switchPage" class="button icon icon-arrow-down dark"><span>contact me</span></a>

                    </div>

                </div>

            </div>
            <!-- .container -->

        </section>
        <!-- section -->

    </div>

</template>

<script>
    export default {
        name: "About",
        data(){
            return{
                state: {
                    urlChange: false
                }
            }
        },
        methods: {
           switchPage(){
                this.state.urlChange = true;
                this.$emit('switchPage', {effect: 'slideUp', component: 'contact'})
           }
        }
    }
</script>

<style scoped>

</style>
