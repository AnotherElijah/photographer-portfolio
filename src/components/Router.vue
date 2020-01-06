<template>
    <div>
        <component v-bind:is="ViewComponent"></component>
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
        },
    }
</script>

<style scoped>

</style>
