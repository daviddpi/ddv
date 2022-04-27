<template>
  <div>
    <div class="text-to-view">
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nemo illum quod facere, impedit eius, perferendis quam minus, veniam in cumque error? Delectus praesentium perspiciatis nobis assumenda. Alias consectetur accusamus atque?
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi, minus quisquam! Aut voluptatum aliquid aspernatur. Temporibus provident, reiciendis dolor inventore velit explicabo officia quam iure eius enim nihil voluptate adipisci?
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Maiores, possimus. Architecto praesentium id dignissimos rem? Quaerat soluta animi debitis voluptatum magni harum. Dolores nobis non, officia tenetur in odio vero.
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Rerum magnam recusandae eligendi nulla? Velit deserunt distinctio tenetur vero commodi officia perspiciatis repudiandae, doloribus voluptatum debitis, voluptatibus ipsa laboriosam doloremque iure!
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Modi sint quaerat numquam fugit, suscipit aliquid laudantium in illum dolorem exercitationem dolore dolor error quos cumque debitis praesentium odit, itaque soluta!
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Vel similique nisi dicta expedita? Accusamus illo aut blanditiis optio nesciunt quam expedita distinctio, quibusdam corrupti totam, sequi dolor ratione ex magnam.
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Perferendis culpa officia blanditiis eligendi a iusto alias impedit officiis obcaecati omnis voluptatibus qui voluptas eum temporibus, maiores iste distinctio error magnam!
    </div>
  </div>
</template>

<script>
import inView from 'in-view'
export default {
    name: "textView",

    methods: {
        randomIntFromInterval(min, max) { // min and max included 
            return (Math.random() * (max - min + 1) + min).toFixed(2)
        },

        transformText(){
            const textView = document.querySelector('.text-to-view');
            textView.innerHTML = textView.textContent.replace(/\S/g, `<span>$&</span>`);

            const letters_text = document.querySelectorAll('.text-to-view span');

            for (let i = 0; i < letters_text.length; i++) {
                const letter_text = letters_text[i];
                letter_text.style.top = this.randomIntFromInterval(-100,100) + "px";
                letter_text.style.left = this.randomIntFromInterval(-50,50) + "px";
                letter_text.style.fontSize = this.randomIntFromInterval(30,70) + "px";
            }
            
            inView('.text-to-view span')
            .on('enter', el => {
                el.style.top = 0 + "px";
                el.style.left = 0 + "px";
                el.style.fontSize = 20 + "px";
            })
        }
    },

    mounted(){
        this.transformText();
    }
}
</script>

<style>
.text-to-view{
    position: relative;
    padding: 0 15px;
}

.text-to-view span{
    position: relative;
    background-color: transparent;

    transition: all 0.4s linear;
}
</style>