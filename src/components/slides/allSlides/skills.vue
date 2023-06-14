<script>
    import Skill from "./skill/skill.vue";
    export default{
        components : {
            Skill
        },
        props : {
            no : Number
        }
    }
</script>
<template>
    <div :style="`transform : translate(${no*100}%,0%);`" class="skills slide">
        <div class="skills_container">
                <h1>My Useless Skill <span class="special">.</span></h1>

                <div class="skillsbox">
                    <Skill
                        :icon="'fa-solid fa-moon'"
                        :header="'Sleeping'"
                        :text="'I can sleep well since I was born into the world.'"
                    />

                    <Skill
                        :icon="'fa-solid fa-a'"
                        :header="'Talking About Anime.'"
                        :text="'I watched upto 30+ anime.So I am expart in this field.'"
                    />

                    <Skill 
                        :icon="'fa-solid fa-utensils'"
                        :header="'Cooking.'"
                        :text="'I don\'t have enough cooking skills. But what I cook is edible'"
                    />
                </div>
            </div>
    </div>
</template>

<style>
.skills{
    display: flex;
    justify-content: center;
    align-items: center;
}

.skills_container{
    max-width: 1000px;
    width: 80%;
    min-width: 270;
    display: flex;
    flex-flow: column wrap;
    align-items: center;
    padding: 20px;
}

.skills_container h1{
    margin-bottom: 50px;
}

.skillsbox{
    width: 100%;
    display: flex;
    flex-flow: row wrap;
    justify-content: space-between;
}

.skill{
    width: 220px;
    display: flex;
    flex-flow: column wrap;
    justify-content: center;
    align-items: center;
    align-content: center;
    text-align: center;
    cursor: pointer;
    position: relative;
}

.skill h3{
    margin: 10px 0px;
}
.skill .skillicon{
    width: 30px;
    height: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 30px;
}

.skillline{
    position: absolute;
    bottom: -6px;
    left:  50%;
    transform: translate(-50%,400%);
    transform-origin: center;
    width: 60px;
    height: 3px;
    border-radius: 3px;
    transition: all 0.3s linear;
}

.lineup .skillline{
    width : 100px;
}

/* media query */

@media only screen and (max-width: 950px) {
    .skill{
        margin: 20px 10px;
    }
}

@media only screen and (max-width: 680px) {
    .skillsbox{
        flex-flow: column wrap;
        align-items: center;
    }
}

@media only screen and (max-width: 380px) { 
    .skills h1{
        font-size: 20px;
    }

    .skill h3{
        font-size: 15px;
    }

    .skill p{
        font-size: 12px;
    }

    .skill{
        margin: 20px 0px;
    }

    .skills_container{
        padding: 2px;
    }
}

/* dark color theme */
.dark .skillicon{
    color : #00ff73;
}

.dark .skillline{
    background-color: #00ff73;
}

/* light color theme */
.light .skillicon{
    color : #ff5100;
}

.light .skillline{
   background-color: #ff5100;
}

</style>