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
        return { ...x, delay: index * 300 };
      });
    }
  },
  methods: {
    onTyped() {
      window.scrollTo(0, document.body.scrollHeight + 100);
    }
  }
};
</script>

<template>
  <div id="messageContent">
      <h1 class="title">Hello You</h1>
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
  <br>
  <br>
  <br>
  <br>
  </div>
</template>

<style lang="css">
#messageContent {
    padding: 1rem;
    width: 100%;
    text-align: left;
}

.custom.caret {
  display: none;
}
</style>
