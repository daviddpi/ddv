<template>
    <div>
        <div class="marquee">
        <div>
            <div>DAVIDE - CRISTINA - ENRICO - SIMONA - ALESSIO - GIUSEPPE - IRA - VIRGINIA - ALESSIA - DAVIDE - CRISTINA - ENRICO - SIMONA - ALESSIO - GIUSEPPE - IRA - VIRGINIA - ALESSIA - DAVIDE - CRISTINA - ENRICO - SIMONA - ALESSIO - GIUSEPPE - IRA - VIRGINIA - ALESSIA - DAVIDE - CRISTINA - ENRICO - SIMONA - ALESSIO - GIUSEPPE - IRA - VIRGINIA - ALESSIA&nbsp;</div>
        </div>
    </div>
    </div>
</template>

<script>
export default {
    name: "TextMarquee",

    methods: {
    
    },

    mounted(){
        const text = document.querySelector('.marquee div');
        text.innerHTML = text.textContent.replace(/\S/g, "<span>$&</span>");
       
    }
}
</script>

<style>
.marquee {
    transform: rotate(-4deg);
    width: 100%;
    font-size: 86px;
    font-family: 'Times New Roman', Times, serif;
    font-weight: bold;
    white-space: nowrap;
    position: absolute;
    top: 10%;
    overflow: hidden;


    color: white;
    -webkit-text-fill-color: black; /* Will override color (regardless of order) */
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: white;
}

.marquee div {
    display: inline-block;
    padding-left: 10%;
    animation: marquee 20s linear infinite;
}

.marquee div:hover{
    animation-play-state: paused;
}

@keyframes marquee {
    0% {
        transform: translate(0, 0);
    }
    100% {
        transform: translate(-80%, 0);
    }
}

.marquee div span:hover{
    -webkit-text-fill-color: white; /* Will override color (regardless of order) */
    font-style: italic;
    padding: 0 5px;
}


</style>