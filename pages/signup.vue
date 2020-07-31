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
                <h1 class="a-spacing-small">Create Account</h1>
                <!-- Your Name -->
                <div class="a-row a-spacing-base">
                  <label for="ap_customer_name" class="a-form-label">Username</label>
                  <input
                    type="text"
                    id="ap_customer_name"
                    class="a-input-text form-control auth-autofocus auth-required-field auth-contact-verification-request-info"
                    v-model.trim="$v.name.$model" :class="{'is-invalid':$v.name.$error, 'is-valid':!$v.name.$invalid}"
                  />
                  <div class="valid-feedback">Your Username is valid</div>
                  <div class="invalid-feedback">
                    <span v-if="!$v.name.required">Username is required.</span>
                    <span v-if="!$v.name.minLength">Username must have at least {{ $v.name.$params.minLength.min }}</span>
                    <span v-if="!$v.name.maxLength">Username must have at most {{ $v.name.$params.maxLength.max }}</span>
                  </div>
                </div>
                <!-- Your Email -->
                <div class="a-row a-spacing-base">
                  <label for="ap_customer_name" class="a-form-label">Email</label>
                  <input
                    type="email"
                    id="ap_customer_email"
                    class="a-input-text form-control auth-autofocus auth-required-field auth-contact-verification-request-info"
                    v-model.trim="$v.email.$model" :class="{'is-invalid':$v.email.$error, 'is-valid':!$v.email.$invalid}"
                  />
                  <div class="valid-feedback">Your email is valid</div>
                  <div class="invalid-feedback">
                    <span v-if="!$v.email.required">Email is required.</span>
                    <span v-if="!$v.email.isUnique">This email is already registered.</span>
                  </div>
                </div>
                <!-- Your Password -->
                <div class="a-row a-spacing-base">
                  <label for="ap_customer_name" class="a-form-label">Password</label>
                  <input
                    type="password"
                    id="ap_customer_password"
                    class="a-input-text form-control auth-autofocus auth-required-field auth-contact-verification-request-info"
                    v-model="password"
                    required
                  />
                  <div class="a-alert-container">
                      <div class="a-alert-content" style="text-align: center;">Password must be at least 6 characters</div>
                  </div>
                </div>
                <!-- Button -->
                <div class="a-row a-spacing-extra-large mb-4">
                    <span class="a-button-primary">
                        <span class="a-button-inner">
                            <span class="a-button-text" @click="onSignup">Create your Account</span>
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
                <hr>
                <div class="a-row">
                    <b>
                        Already have an account?
                        <nuxt-link to="/login" class="a-link-emphasis">Sign in</nuxt-link>
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
import { required, email, minLength, maxLength } from 'vuelidate/lib/validators'

export default {
    middleware: 'auth',
    auth: 'guest',
    layout: 'none',
    data() {
        return {
            name: '',
            email: '',
            password: ''
        }
    },
    validations: {
      name: {
        required,
        minLength: minLength(5),
        maxLength: maxLength(15)
      },
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
        async onSignup() {
            try {
                let userData = {
                    name: this.name,
                    email: this.email,
                    password: this.password
                };

                // let response = await this.$axios.$post('http://localhost:3000/api/auth/signup', userData);
                let response = await this.$axios.$post('/api/auth/signup', userData);
                console.log(response);

                if (response.success) {
                    this.$auth.loginWith('local', {
                        data: {
                            email: this.email,
                            password: this.password
                        }
                    });
                    this.$router.push('/');
                }
            } catch (err) {
                console.log(err);
            }
        }
    }
};
</script>

<style scoped>
</style>
