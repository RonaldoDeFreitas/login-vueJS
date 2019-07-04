<script>
  import SignIn from "./sign-in";
  import SignUp from "./sign-up";

  export default {
    components: {
      SignIn,
      SignUp
    },
    
    data () {
      return {
        navigation: 'signin'
      }
    },

    methods: {
      navigate () {
        this.$bus.$emit('navigate', this.navigation)
        
      },
      doSignIn (obj) {
        
        //fingir que há uma chamada AJAX
        window.console.log(obj)

      },
      doSignUp (obj) {
        
        //fingir que há uma chamada AJAX
        window.console.log(obj)

      }
    }
  };
</script>


<template>
  <div>
    <div class="login-wrap">
      <div class="login-html">

        <input 
          id="tab-1" 
          type="radio"
          value="signin"
          @change="navigate"
          v-model="navigation"
          name="tab" 
          class="sign-in" 
          checked
        />
        <label for="tab-1" class="tab">Sign In</label>

        <input 
          id="tab-2" 
          type="radio"
          value="signup"
          @change="navigate"
          v-model="navigation" 
          name="tab" 
          class="sign-up"
        />
        <label for="tab-2" class="tab">Sign Up</label>

        <div class="login-form">
          <sign-in @do-sign-in="doSignIn" />
          <sign-up @do-sign-in="doSignUp"/>
        </div>

      </div>
    </div>
  </div>
</template>

<style src="./styles.css"></style>

