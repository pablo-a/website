<script>
const MESSAGES = [
  { content: "Salut Flo\n", delay: 50 },
  { content: "C'est compliqué pour moi de parler mais je vais tenter de mener à bien cette tâche.\n" },
  { content: "Car je te le dois et j'aimerais pouvoir réparer notre relation.\n" },
  { content: "C'est vraiment insupportable pour moi de t'avoir fait du mal\n", },
  { content: "Well c'est vraiment de la merde Pablo\n", },
  { content: "va falloir retravailler ce texte\n", },
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
        this.messages.forEach(function(message, index, array)  {
            if (index === 0) {
                return
            }
            const prevMessage = array[index - 1]
            const delay = prevMessage['delay'] + prevMessage['content'].length * 70 + 2000

            array[index]['delay'] = delay

            }
        );
        return this.messages

    //   return this.messages.map((x, index) => {
    //     return { ...x, delay: index * 1000 };
    //   });
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
    background-color: black;
    border: 1px solid black;
    border-radius: 1%;
    padding: 1rem;
    margin: 1rem;
    width: 100%;
    text-align: left;
}

.vue-typer .custom.char {
    color: white;
}

.custom.caret {
  display: none;
}
</style>
