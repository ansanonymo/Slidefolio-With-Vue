<script>
    import SocialIcon from "./socialicon/socialicon.vue"

    export default{
        components : {
            SocialIcon
        },
        props : {
            no : Number
        }
    }
</script>

<template>
    <div :style="`transform : translate(${no*100}%,0%);`" class="contactme slide">
        <div class="contactme_container">
            <h1>Contact Me <span class="special">.</span></h1>

            <ul class="socialbox">
                <SocialIcon 
                    :link = "'https://github.com/Tazri'"
                    :icon = "'fa-brands fa-square-github'"
                />

                <SocialIcon 
                    :link="'https://codepen.io/md-tazri'"
                    :icon="'fa-brands fa-codepen'"
                />

                <SocialIcon 
                    :link="'https://twitter.com/MdTazri'"
                    :icon="'fa-brands fa-square-twitter'"
                />

                <SocialIcon 
                    :link="'https://www.facebook.com/tazri.md/'"
                    :icon="'fa-brands fa-square-facebook'"
                />
            </ul>

            <textarea 
                name="" 
                id="" 
                cols="30" 
                rows="10" 
                placeholder="You can write anything here, but this is waste of time...."></textarea>
            <button>Useless Send Button.</button>
        </div>
    </div>
</template>

<style>
/*
slide contactme
contactme_container
socialbox
socialicon
*/

.contactme{
    display: flex;
    justify-content: center;
    align-items: center;
}

.contactme_container{
    display: flex;
    flex-flow: column wrap;
    align-items: center;
    padding: 5px;
    max-width: 1000px;
    width: 80%;
    min-width: 270;
}

.contactme_container h1{
    margin-bottom: 20px;
}

.contactme_container .socialbox{
    list-style: none;
    display: flex;
    width: 100%;
    margin-bottom: 40px;
    max-width: 400px;
    width:  80%;
    justify-content: space-between;
}

.contactme_container .socialbox li{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 50px;
    height: 50px;
    font-size: 40px;
    cursor: pointer;
    transition: all 0.3s linear;
    position: relative;
}

.socialline{
    position: absolute;
    bottom: 0px;
    left: 50%;
    transform: translate(-50%,0%);
    height: 2px;
    border-radius: 4px;
    width: 2px;
    transform-origin: left;
    transition: all 0.3s linear;
}

.contactme .socialbox li a{
    transition: all 0.3s linear;
}

.contactme .socialbox li a:hover{
    transform: translate(0%,-20%);
}
.lineup .socialline{
    width : 22px;
}

.contactme h3{
    margin-bottom: 10px;
}

.contactme textarea{
    border-radius: 7px;
    font-size: 16px;
    max-width: 500px;
    max-height: 400px;
    width: 100%;
    resize: both;
    margin-bottom: 10px;
    transition: all 0.3s linear;
    padding: 10px 8px;
}

.contactme button{
    padding: 8px 12px;
    font-size: 15px;
    cursor: pointer;
    border-radius: 9px;
}

.contactme button:hover{
    transition: all 0.3s linear;
}

@media only screen and (max-width: 720px) {
    .contactme_container h1{
        font-size: 22px;
    }

    .contactme_container .socialbox li{
        width: 30px;
        height: 30px;
        font-size: 20px;
    }
}

/* dark color theme */
.dark .contactme_container .socialbox li a{
    color: #00ff73;
}

.dark .socialline{
    background-color: #00ff73;
}

.dark .contactme textarea{
    border: 2px solid #434444;
}

.dark .contactme textarea:focus{
    border: 2px solid #00ff73;
}

.dark .contactme button{
    border: 2px solid #00ff73;
    background-color: #00ff73;
    color: #101010;
}

.dark .contactme button:hover{
    background-color: #101010;
    color: #00ff73;
}

/* light color theme */
.light .contactme_container .socialbox li a{
    color: #ff5100;
}

.light .socialline{
    background-color: #ff5100;
}

.light .contactme textarea{
    border: 2px solid #434444;
}

.light .contactme textarea:focus{
    border: 2px solid #ff5100;
}

.light .contactme button{
    border: 2px solid #ff5100;
    background-color: #ff5100;
    color: #101010;
}

.light .contactme button:hover{
    background-color: #ffffff;
    color: #ff5100;
}
</style>