<script>
    export default{
        props : {
            no : Number
        },

        data(){
            return {
                isLineUp : false
            }
        },

        methods : {
            mouseEnter(){
                this.isLineUp = true;
            },
            mouseLeave(){
                this.isLineUp = false;
            }
        }
    }
</script>

<template>
    <div :style="`transform : translate(${no*100}%,0%);`" class="aboutme slide">
        <div class="aboutme_container">
                <div class="aboutme_container-img">
                    <img src="./img/profile_2.jpg" alt="ANS anonymo">
                    <div class="aboutdot"></div>
                </div>

                <div 
                    @mouseenter="mouseEnter" 
                    @mouseleave="mouseLeave"
                    class="aboutme_container-text" 
                    id="aboutmetext">
                    <h2>About me <span class="special">.</span></h2>
                    <p>I am a human. I have two eye, two hand, two ear and one head. Also I have a brain inside my head. Also I look like a human. I live in earth. It is a blue planet. Don't click below button to read more about me.This button is useless. It's dose not work. Stop reading about me. Go do your business or work. Here some more useless text Lorem ipsum dolor sit amet consectetur adipisicing elit. Inventore adipisci doloribus incidunt perspiciatis voluptatem beatae labore delectus alias debitis earum <span class="special">!</span></p>
                    <button>Useless Button</button>
                    <div 
                        :class="isLineUp ? 'line lineup' : 'line'" 
                        id="aboutline"></div>
                </div>
            </div>
    </div>
</template>


<style>
.aboutme{
    display: flex;
    justify-content: center;
    align-items: center;
}

.aboutme_container{
    display: flex;
    flex-flow: row wrap;
    justify-content: space-around;
    align-items: center;
    min-width: 270px;
    width: 80%;
    max-width: 1120px;
}

.aboutme_container-img{
    width: 260px;
    height: 260px;
    border-radius: 5px;
    cursor: pointer;
}

.aboutme_container-img img{
    width: 100%;
    height: 100%;
    border-radius: 5px;
    transform: rotate(5deg);
    transition: all 0.4s linear;
}

.aboutme_container-img img:hover{
    transform: rotate(0deg);
}

.aboutme_container-text{
    min-width: 260px;
    max-width: 500px;
    min-height: 260px;
    display: flex;
    flex-flow: column wrap;
    align-items: flex-start;
    justify-content: space-between;
    position: relative;
    padding: 10px;
}

.line{
    position: absolute;
    width: 4px;
    height: 60px;
    right: 0px;
    bottom: 0px;
    transform: translate(100%,0%);
    border-radius: 5px;
    transform-origin: bottom;
    transition: all 0.2s linear;
}

.aboutme_container-text .lineup{
    height: 100px;
}

.aboutme_container-text h2{
    font-size: 27px;
}

.aboutme_container-text p {
    margin: 20px 0px;
    text-align: justify;
    text-align-last: left;
}

.aboutme_container-text button{
    padding: 8px 10px;
    font-size: 23;
    cursor: pointer;
    border-radius: 5px;
    transition: all 0.3s linear;
}

.aboutme_container-img{
    position: relative;
}

.aboutme_container-img .aboutdot{
    position: absolute;
    width: 10px;
    height: 10px;
    border-radius: 50%;
}

/* media query */

@media only screen and (max-width: 1000px) {
    .aboutme_container{
        display: flex;
        flex-flow: column wrap;
        min-width: 270px;
        width: 80%;
        max-width: 1120px;
        align-items: center;
    }

    .aboutme_container-img{
        margin-bottom: 30px;
    }
}

@media only screen and (max-width: 600px) {
    .aboutme_container-img{
      width: 200px;
      height: 200px;
      margin-bottom: 40px;
    }

    .aboutme_container-text{
        min-height: 200px;
    }

    .aboutme_container-text h2{
        font-size: 18px;
    }

    .aboutme_container-text p{
        font-size: 10px;
    }

    .aboutme_container-text button{
        padding: 5px 7px;
        font-size: 13px;
    }
}


/* dark color theme */
.dark .aboutme_container-text button{
    color: #101010;
    background-color: #00ff73;
    border: 1px solid #00ff73;
}

.dark .aboutme_container-text button:hover{
    color: #00ff73;
    background-color: #101010;
}

.dark .aboutme_container-text .line{
    background-color: #00ff73;
}

.dark .aboutme_container-text p {
    color: #b5b6b8;
}

.dark .aboutme_container-img{
    background-color: #00ff73;
}

.dark .aboutme_container-img .aboutdot{
    background-color: #00ff73;
}

/* light color theme */
.light .aboutme_container-text button{
    color: #ffffff;
    background-color: #ff5100;
    border: 1px solid #ff5100;
}

.light .aboutme_container-text button:hover{
    color: #ff5100;
    background-color: #ffffff;
}

.light .aboutme_container-text .line{
    background-color: #ff5100;
}

.light .aboutme_container-text p {
    color: #6b6b6b;
}

.light .aboutme_container-img{
    background-color: #ff5100;
}

.light .aboutme_container-img .aboutdot{
    background-color: #ff5100;
}
</style>