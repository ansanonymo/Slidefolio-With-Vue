<script>
    export default{
        props : {
            icon : String,
            header : String,
            price : String,
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
    <div 
        :class="isLineUp ? 'service lineup' : 'service'"
        @mouseenter="mouseEnter"
        @mouseleave="mouseLeave">
        <div class="serviceicon">
            <i :class="icon"></i>
            <div class="serviceline"></div>
        </div>
        <h4>{{ header }}</h4>
        <h3>{{ price }}</h3>
        <p>{{  text }}</p>
        <button>Hire</button>
    </div>
</template>