<template>
    <div class="login">
        <div class="form">
            <form class="login-form">
                <span >SIGN UP</span>
                <input v-model="firstname" type="text" placeholder="first name" required />
                <input v-model="lastname" type="text" placeholder="last name" required />
                <input v-model="email" type="email" placeholder="email" required />
                <input v-model="position" type="text" placeholder="position" required />
                <div class="pw"><input :type="showpassword ? 'text' : 'password'" v-model="password" placeholder="password" required />
                <i @click="shwpassw" v-if="showpassword">
                  <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#5C415D" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="feather feather-eye-off"><path d="M17.94 17.94A10.07 10.07 0 0 1 12 20c-7 0-11-8-11-8a18.45 18.45 0 0 1 5.06-5.94M9.9 4.24A9.12 9.12 0 0 1 12 4c7 0 11 8 11 8a18.5 18.5 0 0 1-2.16 3.19m-6.72-1.07a3 3 0 1 1-4.24-4.24"></path><line x1="1" y1="1" x2="23" y2="23"></line></svg>
                </i>
                <i @click="shwpassw" v-else>
                  <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#5C415D" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="feather feather-eye"><path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"></path><circle cx="12" cy="12" r="3"></circle></svg>  
                </i></div>
                <input :type="showpassword ? 'text' : 'password'"  v-model="confirmpassword"  placeholder="confirm password" required />
                <div class="check">
                    <input v-model="TandC" type="checkbox" name="" id="">
                    <span>I've read and agree with T&C</span>
                </div>
                <div><button :disabled='!TandC'>sign up</button></div>
                <div class="extra-line">
                    <span>Already have an account?</span>
                    <nuxt-link to="/login">Sign In</nuxt-link>
                  </div>
            </form>  
        </div>
    </div>
</template>

<script>
export default {
  layout: 'plain',
  data(){
    return{
      firstname:'',
      lastname: '',
      position: '',
      email: '',
      password: '',
      confirmpassword: '',
      TandC: false,
      showpassword: false,
    }
  },
  methods:{
    shwpassw(){
      this.showpassword = !this.showpassword;
      console.log(this.showpassword)
    }
  }
}
</script>

<style lang="scss">
body {
//   background: linear-gradient(90deg, $primary-color 0%, #182848 100%);
    background-color: rgba($primary-color, 0.4);
    // filter: blur(5px);
}

.login {
  width: 360px;
  padding: 8% 0 0;
  margin: auto;
  font-family: 'Comfortaa', cursive;
}
.pw{
  position: relative;
}
i{
  display: inline-block;
  color: #888;
  font-size: 0.8em;
  position: absolute;
  bottom: 26px;
  right: 10px;
  cursor: pointer;
}

.form {
  position: relative;
  z-index: 1;
  background: #FFFFFF;
  border-radius: 10px;
  max-width: 360px;
  margin: 0 auto 100px;
  padding: 45px;
  text-align: center;
}

.form input {
  outline: 0;
  background: #f2f2f2;
  width: 100%;
  border: 0;
  border-radius: 5px;
  margin: 0 0 15px;
  padding: 15px;
  box-sizing: border-box;
  font-size: 14px;
  font-family: 'Comfortaa', cursive;
}
.form input[type=checkbox]{
    display: inline;
}

.form input:focus {
  background: #dbdbdb;
}

.form button {
  font-family: 'Comfortaa', cursive;
  text-transform: uppercase;
  outline: 0;
  background: $primary-color;
  width: fit-content;
  border: 0;
  border-radius: 5px;
  padding: 10px 15px;
  color: #FFFFFF;
  font-size: 14px;
  -webkit-transition: all 0.3 ease;
  transition: all 0.3 ease;
  cursor: pointer;
}

.form button:active {
  background: $primary-color;
}
.form button:hover{
  background-color: rgba($primary-color, 0.9);
}

.form span {
  font-size: 1em;
  color: $primary-color;
}
.check{
    display: flex;
    justify-content: flex-start;

    input{
        width: fit-content;
        padding: 6px;
    }
    
}
.check > span{
        font-size: 0.7em;
         width: 1000%;
         margin-left: 15px;
    }
.extra-line{
    font-size: 0.7em;
    margin-top: 10px;
}
@media only screen and (max-width: 450px){
  .login{
    margin-top: 20vh;
    width: 90vw;
     padding: 4% 0 0;
  }

 i{
  position: absolute;
  bottom: 18px;
  right: 8px;
}

.form {
  max-width: 360px;
  padding: 30px;
}

.form input {
  margin: 0 0 8px;
  padding: 8px;
  font-size: 14px;
}

.form button {
  padding: 10px;
  color: #FFFFFF;
  font-size: 12px;
}

.extra-line > span{
    font-size: 1em;
    margin-top: 10px;
}
}

</style>