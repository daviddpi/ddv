<template>
    <div>
        <FollowMouse />
        <main>
            <section class="intro">
                <div class="container-fluid">
                    <div class="row">
                        <div class="col-12 d-flex justify-content-between align-items-center">
                            <div class="textLogo">
                                <div class="digital" @click="clickOrEnter" @mouseover="clickOrEnter">
                                    Digital
                                </div>
                                <div class="design" @click="clickOrEnter" @mouseover="clickOrEnter">
                                    Design
                                </div>
                                <div class="vue" @click="clickOrEnter" @mouseover="clickOrEnter">
                                    Vue
                                </div>
                            </div> 
                        </div>
                    </div>
                </div>
            </section>
            <section>
                <TextMarquee />
            </section>
            <div>
                <!-- <TextView /> -->
            </div>
        </main>
        <Stregatto />
    </div>

</template>

<script>
import FollowMouse from './FollowMouse.vue'
import Stregatto from './Stregatto.vue'
import TextMarquee from './TextMarquee.vue'
// import TextView from './TextView.vue'

export default {
    name: "Main",

    components: {
        FollowMouse,
        Stregatto,
        TextMarquee,
        // TextView

    },

    data () {
      return {

      }
    },

    methods: {
        introLogo(){
             
            const textLogo = document.querySelectorAll('.textLogo div');
            textLogo.forEach( el => {

                el.innerHTML = el.textContent.replace(/\S/g, "<span>$&</span>");
            })
        },

        clickOrEnter(e){
            
            const logoAnimate = e.target.parentElement;
            const lengthLogoAnimate = logoAnimate.children;
            let delay = 0.25;

            for (let index = 0; index < lengthLogoAnimate.length; index++) {
                const el = lengthLogoAnimate[index];
                if(index > 0 && el.tagName.toLowerCase() == 'span'){

                    console.log(el)
                    el.style.animation = `visibleLogo 2.5s ${delay}s ease`;
                    delay += 0.05;
                    setInterval(() => {
                        
                        el.style.opacity = 1;
                    }, 500);
                }
            }
        }

    },

    mounted(){
        this.introLogo();
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cabin:wght@700&display=swap');

    main{
        overflow-x: hidden;
        background-color: black;
    }

    section{
        position: relative;
        height: 100vh;
        width: 100%;
    }

    .intro{
        height: 100vh;
        color: white;
    }

    .container-fluid{
        width: 100%;
        height: 100%;
    }

    .row{
        width: 100%;
        height: 100%;
    }

    .col-12{
        width: 100%;
        height: 100%;
    }

    .textLogo{
        font-family: 'Cabin', sans-serif;
        font-size: 100px;
        text-transform: uppercase;
    }

    .textLogo div span{
        opacity: 0;
        display: inline-block;
    }

    .textLogo div span:first-child{
        opacity: 1;
    }

    .digital span:first-child{
        text-shadow: 0 0 10px #fff, 0 0 20px #fff, 0 0 30px cornflowerblue, 0 0 40px cornflowerblue, 0 0 50px cornflowerblue, 0 0 60px cornflowerblue, 0 0 70px cornflowerblue;
    }

    .digital span{
        color: cornflowerblue;
    }


    .vue span:first-child{
        text-shadow: 0 0 10px #fff, 0 0 20px #fff, 0 0 30px #3fb984, 0 0 40px #3fb984, 0 0 50px #3fb984, 0 0 60px #3fb984, 0 0 70px #3fb984;

    }

    .vue span{
        color: #3fb984;
    }


    .design span:first-child{
        text-shadow: 0 0 10px #fff, 0 0 20px #fff, 0 0 30px #ff4da6, 0 0 40px #ff4da6, 0 0 50px #ff4da6, 0 0 60px #ff4da6, 0 0 70px #ff4da6;
    }

    .design span {
        color: #ff4da6;
    }

    @keyframes visibleLogo {
        0%{
            transform: translateY(100%);
            opacity: 0;
        }
        100%{
            transform: translateY(0);
            opacity: 1;
        }
    }

</style>