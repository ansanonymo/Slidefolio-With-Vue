<script>
import Mode from "./modes/modes.vue";
import Indicator from "./indicator/indicator.vue";
import Slides from './slides/slides.vue';
export default{
    // components
    components : {
        Mode,
        Indicator,
        Slides
    },

    // state
    data(){
        return {
            current_mode : "dark",
            activateSlide : 'home'
        }
    },

    methods : {
        // mode button
        onClickMode(e){
            this.current_mode = this.current_mode == 'dark' ? "light" : 'dark';

            if(this.current_mode == "dark"){
                document.getElementById("fabicon").href = "./public/dark.png";
            }else{
                document.getElementById("fabicon").href = "./public/light.png";
            }
        },
        changeSlide(name){
            this.activateSlide = name;
        }
    }
}
</script>


<template>
    <div :class="current_mode == 'dark' ? 'body dark' : 'body light'">
        <!-- slides contains all slide home, aboutme, skills, services and contactme -->
        <Slides :acivateSlideName="activateSlide" />

        <!-- mode changing button -->
        <Mode 
            :className="current_mode == 'dark' ? 'mode' : 'mode change'" 
            :handler="onClickMode"
            />

        <!-- incator for changing slide-->        
        <Indicator :changeSlide = "changeSlide" />
    </div>
</template>

<style>

/* color for dark theme */
.dark{
    background-color: #101010;
    color: #f0f8ff;
}

.dark .special{
    color: #00ff73;
}

/* color for light theme */
.light{
    background-color: #ffffff;
    color: #101010;
}

.light .special{
    color: #ff5100;
}
</style>