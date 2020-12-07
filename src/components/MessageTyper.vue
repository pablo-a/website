<script>
const MESSAGES = [
  { content: "Salut Flo\n", delay: 50 },
  { content: "Salut ça va\n", delay: 3000 },
  { content: "Salut ça va\n", delay: 4000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 },
  { content: "Salut ça va\n", delay: 5000 }
];

export default {
  name: "MessageTyper",
  data() {
    return {
      messages: MESSAGES
    };
  },
  computed: {
    messagesAutoDelay() {
      return this.messages.map((x, index) => {
        return { ...x, delay: index * 100 };
      });
    }
  },
  methods: {
    onTyped() {
      window.scrollTo(0, document.body.scrollHeight);
    }
  }
};
</script>

<template>
  <div id="messageContent">
    <h3>Message Typer component</h3>

    <vue-typer
      v-for="message in messagesAutoDelay"
      :key="message.id"
      :text="message.content"
      :pre-erase-delay="250000"
      :pre-type-delay="message.delay"
      @typed="onTyped"
      caret-animation="blink"
    ></vue-typer>
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
</style>
