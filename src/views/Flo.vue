<script>
import MessageTyper from "@/components/MessageTyper.vue";


export default {
    name: 'flo',
    components: {
        MessageTyper,
    }
}
</script>

<template>
    <div id="flo">
        <h1>hello Flo</h1>

        <message-typer />
    </div>
</template>

<style>
.custom.caret.pre-erase {
    display: none;
}
</style>