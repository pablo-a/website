<script>
const MESSAGES = [
    {content: 'Salut Flo\n', delay: 50},
    {content: 'Salut ça va\n', delay: 3000},
    {content: 'Salut ça va\n', delay: 4000},
    {content: 'Salut ça va\n', delay: 5000},
]

export default {
    name: 'MessageTyper',
    data() {
        return {
            messages: MESSAGES,
        }
    },
    methods: {
        onComplete() {
            return
        }
    }
}
</script>

<template>
    <div id="messageContent">
        <h3>Message Typer component</h3>
        
        <vue-typer
            v-for="message in messages"
            :key="message.id"
            :text="message.content"
            :pre-erase-delay='250000'
            :pre-type-delay='message.delay'
            caret-animation='blink'></vue-typer>
        <!-- <vue-typer :text="message" :erase-on-complete="false" type-delay='70'></vue-typer><br> -->
    </div>
</template>

<style lang="css">
#messageContent {
    text-align: left;
}

.custom.caret {
    display: none;
}

.custom.caret.pre-erase {
    display: none;
}
.custom.caret.pre-type {
    display: none;
}

</style>