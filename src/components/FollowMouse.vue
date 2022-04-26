<template>
  <div>
    <div class="mouse-cursor">
        <div class="circle"></div>
    </div>
  </div>
</template>

<script>
import $ from 'jquery'

export default {
    name: 'FollowMouse',
    mounted () {
        const cursor = $(".mouse-cursor");
    
        $(document).mousemove(function (e){ 
            
            cursor.animate({
                left: e.pageX,
                top: e.pageY - window.pageYOffset
            }, 0.1);
            
        })
    }   
}
</script>

<style scoped>
.mouse-cursor{
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    height: 120px;
    width: 120px;
    display: flex;
    justify-content: center;
    align-items: center;
    -webkit-box-align: center;
    -webkit-box-pack: center;
    backface-visibility: hidden;

    transition: ease;
}

.circle{
    position: relative;
    height: 42px;
    width: 42px;
    border: 3px solid cornflowerblue;
    border-radius: 50%;

}
</style>