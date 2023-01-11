<template>
    <main>
       <b-container>
            <c-testimonial :items="testimonialItems"/>
       </b-container>
    </main>
</template>

<script>
import CTestimonial from '../components/Testimonial/Testimonial.vue'
export default {
    name:'homePage',

    data() {
        return {
            testimonialItems:[
                {
                    id:1,
                    image:'user1.jpg',
                    name:'Alex Gram',
                    text:'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Egestas purusviverra accumsan in nisl nisi.',
                },
                {
                    id:2,
                    image:null,
                    name:'User',
                    text:'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqu.',
                }
            ],
        }
    },

    components:{
        CTestimonial,
    }
}
</script>
