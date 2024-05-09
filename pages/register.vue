<template>
    <div class="bg">
        <div class="container">
            
                <img class="logo" src="@/static/logo.png" alt="Logo">

                <v-card-text>
                    <v-form ref="form" v-model="valid" lazy-validation>
                        <v-text-field v-model="email" :rules="emailRules" outlined label="E-mail"
                            required prepend-inner-icon="mdi-account"></v-text-field>
                        <v-text-field v-model="password" :rules="passwordRules" outlined label="Password"
                            required prepend-inner-icon="mdi-lock"></v-text-field>
                        <v-text-field v-model="confirmpassword" :rules="confirmpasswordRules" outlined label="Confirm Password"
                            required prepend-inner-icon="mdi-lock"></v-text-field>
                    </v-form>

                    <v-btn  block height="40px" :disabled="!valid" color="success" class="mr-4" @click="validate">
                        SIGN UP
                    </v-btn>
                  
                </v-card-text>


        </div>
    </div>
</template>





<script>
  export default {

    layout: "auth",

    data: () => ({
      valid: true,
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      ],
      valid: true,
      password: '',
      passwordRules: [
        v => !!v || 'Password is required',
      ],
      valid: true,
      confirmpassword: '',
      confirmpasswordRules: [
        v => !!v || 'Password is required',
      ],
    }),

    methods: {
      validate () {
        if(this.$refs.form.validate()) 
            this.$router.push("/login")
        }
    },
  }
</script>


<style scoped>

.bg{
      margin-top: 140px;

    }

.container {
  max-width: 400px;
  margin: 50px auto;
  background-color: #fff;
  padding: 20px;    
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  display: flex;
  flex-direction: column;
  align-items: center;
}
.logo {
  display: flex;
  justify-content: center;
  margin-bottom: 20px;
}

.logo img {
  width: 100px;
}

.button {
    margin: 40px;
    font-size: 14px;
}
</style>