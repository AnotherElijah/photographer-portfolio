<template>
    <div>
        <component @switchPage="switchWithSlide" v-bind:showUpEffect="showUpEffect" v-bind:is="ViewComponent"></component>
    </div>
</template>

<script>
    import Home from "@/components/Home";
    import About from "@/components/About";
    import Contact from "@/components/Contact";
    import Portfolio from "@/components/gallery/Portfolio";

    const routes = {
        '/': Home,
        '/about': About,
        '/contact': Contact,
        '/portfolio': Portfolio
    };

    export default {
        name: "Router",
        components: {
            Home,
            About,
            Contact,
            Portfolio
        },
        computed: {
            ViewComponent () {
                return routes[window.location.pathname]
            }
        },
        methods: {
            forceSwitch(component){
                setTimeout(()=>{
                    window.location.pathname = '/'+component
                },500)
            },
            switchWithSlide: function(emittedData){
                this.showUpEffect = emittedData.effect;
                this.forceSwitch(emittedData.component);
            }
        },
        //switchEffect: slideDown, slideUp
        data(){
            return {
                showUpEffect: null
            }
        },
        created(){
            console.log('created')
        },
        updated(){
            console.log('router updated: '+ this.showUpEffect)
        }
    }
</script>

<style scoped>

</style>
