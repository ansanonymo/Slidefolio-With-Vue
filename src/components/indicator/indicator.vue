<script>
    export default{
        data(){
            return {
                activateButton : "home"
            }
        },

        methods : {
            OnClickLiIcon(e){
                this.activateButton = e.target.dataset.name;
                this.$props.changeSlide(e.target.dataset.name);
            }
        },
        props : {
            changeSlide : Function
        }
    }
</script>

<template>
    <div class="indicator" ref="indicator">
        <ul>
            <li @click="OnClickLiIcon" :class="activateButton == 'home' && 'active'" data-name="home">
                <i @click="OnClickLiIcon" class="fa-solid fa-house" data-name="home"></i>
            </li>
            <li @click="OnClickLiIcon" :class="activateButton == 'aboutme' && 'active'" data-name="aboutme">
                <i @click="OnClickLiIcon" class="fa-solid fa-user" data-name="aboutme"></i>
            </li>
            <li @click="OnClickLiIcon" :class="activateButton == 'skills' && 'active'" data-name="skills">
                <i @click="OnClickLiIcon" class="fa-solid fa-pen" data-name="skills"></i>
            </li>
            <li @click="OnClickLiIcon" :class="activateButton == 'services' && 'active'" data-name="services">
                <i @click="OnClickLiIcon" class="fa-solid fa-briefcase" data-name="services"></i>
            </li>
            <li @click="OnClickLiIcon" :class="activateButton == 'contactme' && 'active'" data-name="contactme">
                <i @click="OnClickLiIcon" class="fa-solid fa-address-book" data-name="contactme"></i>
            </li>
        </ul>
    </div>
</template>

<style>
/* style without color */
.indicator{
    position: absolute;
    bottom: 10px;
    left: 50%;
    transform: translate(-50%,0%);
    z-index: 1;
    display: block;
    transition: all 0.5s ease;
    animation-name: showIndicator;
    animation-duration: 0.4s;
    animation-delay: 1s;
    animation-timing-function: ease;
}

.indicator ul{
    min-width: 240px;
    max-width: 300px;
    margin: 0px;
    padding: 0px;
    list-style: none;
    padding: 10px 10px;
    display: flex;
    flex: row wrap;
    justify-content: space-between;
    border-radius: 5px;
}

.indicator ul li{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 35px;
    height: 35px;
    font-size: 20px;
    cursor: pointer;
    border-radius: 5px;
    transition: all 0.5s linear;
}

/* dark color theme */
.dark .indicator ul{
    background-color: rgba(0, 128, 58, 0.459);
}

.dark .indicator ul .active{
    background-color: #00ff73;
    color: #101010;
}

.dark .indicator ul li:hover{
    background-color: #00ff73;
    color: #101010;
}

/* light color theme */
.light .indicator ul{
    background-color: rgba(255, 81, 0, 0.329);
}

.light .indicator ul .active{
    background-color: #ff5100;
    color: #ffffff;
}

.light .indicator ul li:hover{
    background-color: #ff5100;
    color: #ffffff;
}

@keyframes showIndicator {
    0%{
        transform: translate(-50%,200%);
        display: block;
    }
    100%{
        transform: translate(-50%,0%);
        display: block;
    }
}

</style>