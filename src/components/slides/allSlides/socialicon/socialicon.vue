<script>
    export default{
        props : {
            link : String,
            icon : String 
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
    <li 
        :class="isLineUp ? 'socialicon lineup' : 'socialicon'"
        @mouseenter="mouseEnter"
        @mouseleave="mouseLeave">
        <a :href="link" target="_blank"><i :class="icon"></i></a>
        <div class="socialline"></div>
    </li>
</template>