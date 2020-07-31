<template>
  <div style="margin-top: 50px;" class="registerPage">
    <div class="container">
      <div class="row">
        <div class="col-sm-4"></div>
        <div class="col-sm-4">
          <div class="text-center">
            <nuxt-link to="/">
              <img src="/img/logo-black.png" alt="" />
            </nuxt-link>
          </div>
          <form class="mt-4">
            <div class="a-box a-spacing-extra-large">
              <div class="a-box-inner">
                <h1 class="a-spacing-small">Sign In</h1>
                <!-- Your Email -->
                <div class="a-row a-spacing-base">
                  <label for="ap_customer_name" class="a-form-label"
                    >Email</label
                  >
                  <input
                    type="email"
                    id="ap_customer_email"
                    class="a-input-text form-control auth-autofocus auth-required-field auth-contact-verification-request-info"
                    v-model.trim="$v.email.$model" :class="{'is-invalid':$v.email.$error, 'is-valid':!$v.email.$invalid}"
                  />
                  <div class="valid-feedback">Your email is valid</div>
                  <div class="invalid-feedback">
                    <span v-if="!$v.email.required">Email is required.</span>
                  </div>
                </div>
                <!-- Your Password -->
                <div class="a-row a-spacing-base">
                  <label for="ap_customer_name" class="a-form-label"
                    >Password</label
                  >
                  <input
                    type="password"
                    id="ap_customer_password"
                    class="a-input-text form-control auth-autofocus auth-required-field auth-contact-verification-request-info"
                    v-model="password"
                    required
                  />
                  <div class="a-alert-container">
                    <div class="a-alert-content" style="text-align: center;">
                      Password must be at least 6 characters
                    </div>
                  </div>
                </div>
                <!-- Button -->
                <div class="a-row a-spacing-extra-large mb-4">
                  <span class="a-button-primary">
                    <span class="a-button-inner">
                      <span class="a-button-text" @click="onLogin"
                        >Continue to Login</span
                      >
                    </span>
                  </span>
                  <div class="a-row a-spacing-top-medium a-size-small">
                    <b>
                      By creating a account, you agree to Amazon's
                      <a href="#">Condition of Use</a> and
                      <a href="#">Privacy Policy</a>
                    </b>
                  </div>
                </div>
                <hr />
                <div class="a-row">
                  <b>
                    Don't have an account?
                    <nuxt-link to="/signup" class="a-link-emphasis"
                      >Sign Up</nuxt-link
                    >
                  </b>
                </div>
              </div>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import { required, email } from 'vuelidate/lib/validators'
export default {
    middleware: 'auth',
    auth: 'guest',
    layout: 'none',
  data() {
    return {
      email: '',
      password: ''
    };
  },
  validations: {
    email: { required, email,
      isUnique (value) {
        if (value === '') return true;

        const email_regex = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;

        return new Promise((resolve) => {
          setTimeout(() => {
            // resolve(typeof value === 'string' && value.length % 2 !== 0);
            resolve(email_regex.test(value));
          }, 350 + Math.random() * 300);
        });
      }
    }
  },
  methods: {
    async onLogin() {
      try {
          await this.$auth.loginWith('local', {
            data: {
              email: this.email,
              password: this.password
            }
          });
          this.$router.push('/');
      } catch (err) {
        console.log(err);
        // this.$store.dispatch('snackbar/setSnackbar', {color: 'red', text: 'The email or password is incorrect.'});
      }
    }
  }
};
</script>
