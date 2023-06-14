<script>
    // import all slide
    import Home from "./allSlides/home.vue";
    import AboutMe from "./allSlides/aboutme.vue";
    import Skills from "./allSlides/skills.vue";
    import Services from "./allSlides/services.vue";
    import ContactMe from "./allSlides/contactme.vue";

    const slidePosition = {
        "home" : 0,
        "aboutme" : 1,
        "skills" : 2,
        "services" : 3,
        "contactme" : 4
    }

    export default{
        // state
        data(){
            return {
                position : 0
            }
        },

        // components
        components : {
            Home,
            AboutMe,
            Skills,
            Services,
            ContactMe
        },

        // props
        props : {
            acivateSlideName : String
        },

        methods : {
            getPosition(){
                return slidePosition[this.$props.acivateSlideName];
            }
        }

    }
</script>

<template>
    <div
        :style="`transform : translate(-${getPosition()*100}%,0%)`" 
        class="slides" 
        ref="slides">
        <Home :no="0" />
        <AboutMe :no="1" />
        <Skills :no="2" />
        <Services :no="3" />
        <ContactMe :no="4" />
    </div>
</template>

<style>
.slides{
    width: 100%;
    height: 100%;
    position: relative;
    transition: all 0.6s ease;
}

.slide{
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0px;
    left: 0px;
}
</style>