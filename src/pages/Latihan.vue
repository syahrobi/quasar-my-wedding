<template>
    <q-page padding>
        <button style="position: absolute; right: 10px;"
                @click="counter++">{{counter}}
        </button>
        <input v-model="message" 
               @keyup="handleKeyup"
               @keyup.enter="alertMessage"
               @keyup.esc="clearMessage"
               v-autofocus
               v-bind:class="{ 'error' : message.length > 22 }"
        />
        <button @click="clearMessage">Clear</button>
        <div>{{ message.length }}</div>
        <h5 class="border-grey" 
            v-show="message.length"
            v-if="message.length">{{message}}
        </h5>
        <h6 v-else>No message</h6>
        <hr/>
        <p>Uppercase message: {{messageUppercase}}</p>
        <p>Lowercase message: {{message | messageLowercase}}</p>
    </q-page>    
</template>

<script>
export default {
    data() {
        return{
            message: "hello",
            counter: 0
        }
    },

    computed:{
        messageUppercase(){
            console.log("messageUppercase was fired")
            return this.message.toUpperCase() + this.counter
        }
    },

    methods:{
        clearMessage(){
            this.message = ""
        },

        alertMessage(){
            alert(this.message)
        },

        handleKeyup(e){
            console.log(e)
            if(e.keyCode == "8"){
                this.message = ""
            }
        }
    },

    filters: {
           messageLowercase(value) {
               return value.toLowerCase()
           }
    },

    directives: {
        autofocus: {
            inserted(el){
                el.focus();
            }
        }
    }
}
</script>

<style>
    .border-grey{
        border: 1px solid grey;
    }

    input, button{
        size: 23px;
    }
    .error{
        color: red;
        background: pink;
    }
</style>

