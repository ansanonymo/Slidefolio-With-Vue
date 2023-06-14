<script>
    export default{
        props : {
            no : Number
        }
    }
</script>

<template>
    <div 
        :style="`transform : translate(${no*100}%,0%);`" 
        class="home slide loader_on_1 loader_on_2">

        <div class="home_container">
            <div class="home_container-about">
                <p>Hello, visitors !</p>
                <h2>I am <span class="special">ANS ANONYMO</span>.</h2>
            </div>

            <div class="home_container-img">
                <img src="./img/profile_1.jpg" alt="ANS anonymo">

                <div class="loader loader1" id="loader1"></div>
                <div class="loader loader2" id="loader2"></div>
                <div class="loader loader3" id="loader3"></div>
            </div>

            <p>
               I am a useless Student. This portfolio also useless. Don't Waste your time to read my portfolio.
            </p>

        </div>
        <button>Resume</button>
        
    </div>
</template>

<style>
.home{
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    position: relative;
    user-select: none;
}

.home button{
    position: absolute;
    top: 10px;
    left : 10px;
    padding: 6px 10px;
    cursor: pointer;
    font-size: 15px;
    transition: all 0.3s ease;
    border-radius: 5px;
}


.home_container{
    display: flex;
    flex-flow: column wrap;
    align-items: center;
}

.home_container-about{
    text-align: center;
}

.home_container-img{
    margin-top: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 250px;
    height: 250px;
    border-radius: 50%;
    position: relative;
}

.home_container-img .loader{
    position: absolute;
    border-radius: 50%;
    transition: all 0.4s linear;
}

.loader_on_1 .home_container-img .loader1{
    width: 105%;
    height: 105%;
    animation: loaderrotate 5s linear infinite;
}


.loader_on_2 .home_container-img .loader2{
    position: absolute;
    border-radius: 50%;
    width: 110%;
    height: 110%;
    animation: loaderrotate 5s linear infinite reverse;
}

.loader_on_3 .home_container-img .loader3{
    position: absolute;
    border-radius: 50%;
    width: 115%;
    height: 115%;
    animation: loaderrotate 5s linear infinite;
}


.home_container-img img{
    width: 100%;
    height: 100%;
    border-radius: 50%;
}

.home_container p{
    font-size: 15px;
    margin-top: 28px;
    max-width: 500px;
    text-align: center;
    padding: 0px 10px;
}

/* animation */

@keyframes loaderrotate {
    from{
        transform: rotate(0deg);
    }

    to{
        transform: rotate(360deg);
    }
}

/* dark color theme */
.dark .home_container-about p{
    color: #b5b6b8;
}

.dark .home_container-img .loader1{
    border-top : 2px solid transparent;
    border-bottom: 2px solid transparent;
    border-right: 2px solid #00ff73;;
    border-left: 2px solid #00ff73;
}

.dark .home_container-img .loader2{
    border-top : 2px solid #ff5100;;
    border-bottom: 2px solid #ff5100;;
    border-right: 2px solid transparent;;
    border-left: 2px solid transparent;
}

.dark .home_container-img .loader3{
    border-top : 2px solid transparent;
    border-bottom: 2px solid transparent;
    border-right: 2px solid #00ff73;;
    border-left: 2px solid #00ff73;
}


.dark .home_container p{
    color: rgb(167, 168, 168);
}

.dark .home button{
    border: 2px solid #00ff73;
    background-color: #00ff73;
    color: #101010;
}

.dark .home button:hover{
    background-color: #101010;
    color: #00ff73;
}

/* light color theme */
.light .home_container-about p{
    color: #b5b6b8;
}

.light .home_container-img .loader1{
    border-top : 2px solid transparent;
    border-bottom: 2px solid transparent;
    border-right: 2px solid #ff5100;;
    border-left: 2px solid #ff5100;
}

.light .home_container-img .loader2{
    border-top : 2px solid #00ff73;
    border-bottom: 2px solid #00ff73;
    border-right: 2px solid transparent;;
    border-left: 2px solid transparent;
}

.light .home_container-img .loader3{
    border-top : 2px solid transparent;
    border-bottom: 2px solid transparent;
    border-right: 2px solid #ff5100;;
    border-left: 2px solid #ff5100;
}


.light .home_container p{
    color: rgb(49, 49, 49);
}

.light .home button{
    border: 2px solid #ff5100;
    background-color: #ff5100;
    color: #ffffff;
}

.light .home button:hover{
    background-color: #ffffff;
    color: #ff5100;
}

</style>