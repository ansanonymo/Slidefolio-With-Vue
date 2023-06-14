<script>
export default {
    props : {
        icon : String,
        header : String,
        text : String
    },

    data(){
        return {
            isLineUp : false
        }
    },

    methods : {
        mouseEnter(e){
            this.isLineUp = true;
        },
        mouseLeave(e){
            this.isLineUp = false;
        }
    }
}
</script>

<template>
    <div :class="isLineUp ? 'skill lineup' : 'skill'" @mouseenter="mouseEnter" @mouseleave="mouseLeave">
        <div class="skillicon">
            <i :class="icon"></i>
        </div>
        <h3>{{ header }}</h3>
        <p>{{ text }}</p>
        <div class="skillline"></div>
    </div>
</template>