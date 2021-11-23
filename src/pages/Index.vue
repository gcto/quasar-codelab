<template>
  <q-page class="row items-center justify-evenly">
    <q-btn @click="signIn">Sign in with Google</q-btn>
  </q-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { getAuth, signInWithPopup, GoogleAuthProvider } from 'firebase/auth';


export default defineComponent({
  name: 'PageIndex',
  setup() {
    async function signIn() {
      console.log('Sign in!');

      const provider = new GoogleAuthProvider();
      const auth = getAuth();
      await signInWithPopup(auth, provider);

    }
    return { signIn };
  }
});
</script>
