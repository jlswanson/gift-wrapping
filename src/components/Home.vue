<template>
    <div>
        <h1>Wraps by Jess</h1>

        <p>What is your full name?</p>
        <input type="text" name="name" placeholder="Full Name"/>

        <p>What's your email address?</p>
        <input type="email" name="email" placeholder="Email Address"/>

        <p>What's the best phone number to reach you at?</p>
        <input type="text" name="phone" placeholder="Phone Number"/>

        <input-multiple name="gifts" placeholder="Description" label="Describe each of the gifts you want wrapped."/>
        <button v-on:click="submitForm($event)">Submit</button>
    </div>
</template>

<script>
import InputMultiple from './forms/InputMultiple.vue'

export default {
    name: 'Home',
    components: {
        InputMultiple
    },
    methods: {
        submitForm: function(event) {
            event.preventDefault();
            console.log('submitted');
        }
    }
}
</script>

<style scoped>
    h1 {
        font-weight: 400;
    }
</style>


