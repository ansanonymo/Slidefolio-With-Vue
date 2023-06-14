<script>
    import Service from "./service/service.vue"
    export default{
        components : {
            Service
        },
        props : {
            no : Number
        }
    }
</script>

<template>
    <div :style="`transform : translate(${no*100}%,0%);`" class="services slide">
        <div class="services_container">
                <h1>Service <span class="special">.</span></h1>

                <div class="services_box">
                    <Service
                        :icon="'fa-solid fa-brush'"
                        :header="'Cleaning Floor'"
                        :price="'4000$'"
                        :text="'Clean half centimeter.'"
                    />
                    
                    <Service
                        :icon="'fa-solid fa-utensils'"
                        :header="'Cookcing'"
                        :price="'12000$'"
                        :text="'Coocked a one cup of tea.'"
                    />
                    

                    <Service
                        :icon="'fa-solid fa-comments'"
                        :header="'Talking'"
                        :price="'41000$'"
                        :text="'Only one minute'"
                    />
                </div>
            </div>
    </div>
</template>

<style>
/* services
services_container
services_box

service

serviceicon */



.services{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-flow: column wrap;
}

.services_container{
    max-width: 1000px;
    width: 80%;
    min-width: 270;
    display: flex;
    flex-flow: column wrap;
    align-items: center;
    padding: 20px;
}


.services h1{
    margin-bottom: 50px;
}


.services_box{
    width: 100%;
    display: flex;
    flex-flow: row wrap;
    justify-content: space-between;
}

.service{
    display: flex;
    flex-flow: column wrap;
    align-items: center;   
    align-content: center;
    justify-content: center;
    cursor: pointer;
    min-width: 250px;
}

.serviceicon{
    width: 50px;
    height: 50px;
    font-size: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 4px;
    position: relative;
}


.service h4{
    font-weight: 300;
    font: 15px;
}

.service h3{
    font-size: 25px;
    margin: 5px 0px;
}

.service p{
    font-size: 15;
}

.service button{
    margin-top: 12px;
    padding: 8px 12px;
    font-size: 18px;
    border-radius: 8px;
    cursor: pointer;
    transition: all 0.3s linear;
}

.serviceline{
    width: 8px;
    height: 4px;
    position: absolute;
    bottom: 0%;
    left: 50%;
    transform: translate(-50%,0%);
    border-radius: 3px;
    transform-origin: center;
    transition: all 0.3s linear;
}

.lineup .serviceline{
    width: 40px;
}

@media only screen and (max-width: 950px) {
    .service{
        margin: 20px 6px;
    }

    .serviceline{
        height: 2px;
    }
}

@media only screen and (max-width: 722px) {
    .service{
        margin: 10px 0px;
    }


    .services_box{
        flex-flow: column wrap;
        align-items: center;
    }

    .service{
        min-width: auto;
    }

    .services h1{
        font-size: 18px;
        margin-bottom: 30px;
    }

    .service h4{
        font-size: 14px;
    }

    .service h3{
        font-size: 18px;
        margin: 2px 0px;
    }

    .service p{
        font-size: 12px;
    }
    
    
    .serviceicon{
        width: 30px;
        height: 30px;
        font-size: 18px;
        display: flex;;
        margin-bottom: 4px;
    }

    .service button{
        margin-top: 5px;
        padding: 4px 10px;
        font-size: 12px;
        border-radius: 8px;
        cursor: pointer;
        transition: all 0.3s linear;
    }

    .serviceline{
        height: 1px;
    }
}


/* dark color theme */
.dark .serviceline{
    background-color: #00ff73;
}

.dark .serviceicon,.dark .service h3{
    color: #00ff73;
}

.dark .service button{
    border: 1px solid #00ff73;
    color: #101010;
    background-color: #00ff73;
}

.dark .service button:hover{
    color: #00ff73;
    background-color: #101010;
}

/* light color theme */
.light .serviceicon{
    color: #ff5100;
}

.light .serviceicon,.light .service h3{
    color: #ff5100;
}

.light .service button{
    border: 1px solid #ff5100;
    color: #ffffff;
    background-color: #ff5100;
}

.light .service button:hover{
    color: #ff5100;
    background-color: #ffffff;
}
</style>