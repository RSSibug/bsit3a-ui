<template>
    <div class="bg">
        <div class="container">
            
                <img class="logo" src="@/static/logo.png" alt="Logo">

                <div class="social">
                </div>
                
                <v-card-text>
                  <v-row>
                    <v-col cols="12" md="6">
                      <v-btn style="width: 140px;">
                        <v-icon color="red">mdi-google</v-icon>
                        Google
                      </v-btn>
                    </v-col>

                    <v-col cols="12" md="6">
                      <v-btn style="margin-left: 14px  ;">
                        <v-icon color="primary">mdi-facebook</v-icon>
                        Facebook
                      </v-btn>
                    </v-col>


                  </v-row>
                </v-card-text>
               

      

                <v-card-text>
                    <v-form ref="form" v-model="valid" lazy-validation>
                        <v-text-field v-model="email" :rules="emailRules" outlined label="E-mail"
                            required prepend-inner-icon="mdi-account"></v-text-field>
                        <v-text-field v-model="password" :rules="passwordRules" outlined label="Password"
                            required prepend-inner-icon="mdi-lock"></v-text-field>
                    </v-form>

                    <v-btn  block height="40px" :disabled="!valid" color="success" class="mr-4" @click="validate">
                        SIGN IN
                    </v-btn>
                    <div style="text-align: center;">
                    <a href="register" style="display: inline-block; margin-top: 4px;">Create an account</a>
                </div>
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
    }),

    methods: {
      validate () {
        if(this.$refs.form.validate()) {
            this.$router.push("/dashboard")
        }
       
        
      },
    },

  }
</script>

<style scoped>
    .bg{
      margin-top: 120px;

    }

    .social{

 
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