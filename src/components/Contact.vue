<template>
    <!-- wrapper -->
    <div class="wrapper">
        <!-- section -->
        <section class="section page contact">

            <!-- .container -->
            <div class="container">

                <div class="row">

                    <div class="cover fullscreen one-half column height-100">

                        <div class="background image fill" data-url="assets/images/contact/background.jpg"></div>

                    </div>

                    <div class="content one-half column">

                        <span class="margined">Contact Me</span>

                        <h2 class="title">Request a Quote... or Say Hi!</h2>

                        <div class="devider margined"></div>

                        <a href="mailto:email@domain.com" class="underline" target="_blank">info@chrisblack.com</a>

                        <p class="text">+1-855-366-2349</p>

                        <p class="text">23 South Broadway, Suite 11, Salem,<br>NH 03079, USA</p>

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
        name: "Contact",
        props: ['showUpEffect'],
        beforeMount() {
            console.log('Contact effect: '+this.showUpEffect)
        },
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
                this.$emit('switchPage', {effect: 'slideDown', component: 'about'})
            }
        }
    }
</script>

<style scoped>

</style>
