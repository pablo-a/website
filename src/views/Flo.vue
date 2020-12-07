<script>
import MessageTyper from "@/components/MessageTyper.vue";

// social Network -> Pinterest
//

export default {
  name: "flo",
  components: {
    MessageTyper
  },
  data() {
      return {
          password: '',
      }
  },
  computed: {
      formCorrectlyAnswered() {
          return this.password == "pablo"
      },
  }
};
</script>

<template>
  <div id="flo" class="container">

    <transition name="password">
        <div class="protection">
            <h1 class="title">Are you Florence ?</h1>
            <div class="form" v-if="!formCorrectlyAnswered">
                <div class="field">
                    <label class="label">Mot de passe</label>
                    <div class="control">
                        <input v-model="password" class="input input-password" type="password" placeholder="the password">
                    </div>
                </div>
            </div>
        </div>
    </transition>

    <message-typer v-if="formCorrectlyAnswered"/>
  </div>
</template>

<style>


#flo.password-enter-active, #flo.password-leave-active {
  transition: bounce-in 3s;
}
#flo.password-enter, #flo.password-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}

</style>
