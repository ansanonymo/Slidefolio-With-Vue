<script>
    export default{
        data(){
            return{

            }
        },
        props : {
            className : String,
            handler : Function
        }
    }
</script>

<template>
    <div class="modes">
        <div :class="className" @click="handler" ref="mode">
            <div class="darkmode">
                <i class="fa-solid fa-moon"></i>
            </div>
            <div class="lightmode">
                <i class="fa-solid fa-sun"></i>
            </div>
        </div>
    </div>
</template>

<style>
/*
     mode common css
*/

.modes{
    position: absolute;
    top: 10px;
    right: 10px;
    width: 35px;
    height: 35px;
    overflow: hidden;
}

.mode{
    width: 100%;
    height : 100%;
    cursor: pointer;
    transition: all 0.3s linear;
}

.modes .change{
    transform: translate(0%,-100%);
}

.modes .mode div{
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 5px ;
}

.modes .mode div i{
    font-size: 22px;
}

/* color theme */
.modes .darkmode{
    background-color: #00ff73;
    color: #101010;
}

.modes .lightmode{
    color: #ff5100;
}
</style>