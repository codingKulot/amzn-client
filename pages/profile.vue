<template>
  <main>
    <div class="container-fluid c-section">
      <div class="row">
        <div class="col-sm-4"></div>
        <div class="col-sm-4">
          <div class="a-spacing-top-medium"></div>
          <h2>Profile Page</h2>
          <a href="#" @click="onLogout">Logout</a>
          <form>
              <!-- Name -->
            <div class="a-spacing-top-medium">
              <label>Name</label>
              <input class="a-input-text" style="width: 100%" :placeholder="$auth.$state.user.name" required
              v-model.trim="$v.name.$model" :class="{'is-invalid':$v.name.$error, 'is-valid':!$v.name.$invalid}"
              />
              <div class="valid-feedback">Your Username is valid</div>
              <div class="invalid-feedback">
                <span v-if="!$v.name.required">Username is required.</span>
                <span v-if="!$v.name.minLength">Username must have at least {{ $v.name.$params.minLength.min }}</span>
                <span v-if="!$v.name.maxLength">Username must have at most {{ $v.name.$params.maxLength.max }}</span>
              </div>
            </div>
            <!-- Email -->
            <div class="a-spacing-top-medium">
              <label>Email</label>
              <input class="a-input-text" style="width: 100%" :placeholder="$auth.$state.user.email" required
              v-model.trim="$v.email.$model" :class="{'is-invalid':$v.email.$error, 'is-valid':!$v.email.$invalid}"
              />
              <div class="valid-feedback">Your email is valid</div>
                <div class="invalid-feedback">
                  <span v-if="!$v.email.required">Email is required.</span>
                  <span v-if="!$v.email.isUnique">This email is already registered.</span>
                </div>
            </div>
            <!-- Password -->
            <div class="a-spacing-top-medium">
              <label>Password</label>
              <input type="password" class="a-input-text" style="width: 100%" v-model="password" required/>
            </div>
            <!-- Button -->
            <hr />
            <div class="a-spacing-top-small">
              <span class="a-button-register">
                <span class="a-button-inner">
                  <span class="a-button-text" @click="onUpdateProfile"
                    >Update Profile</span
                  >
                </span>
              </span>
            </div>
          </form>
          <br>
        </div>
        <div class="col-sm-4"></div>
      </div>
    </div>
  </main>
</template>

<script>
import { required, email, minLength, maxLength } from 'vuelidate/lib/validators'

export default {
    data() {
        return {
            name: '',
            email: '',
            password: ''
        };
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
      async onUpdateProfile() {
        let userData = {
          name: this.name,
          email: this.email,
          password: this.password
        };
        try {
          // let response = await this.$axios.$put('http://localhost:3000/api/auth/user', userData);
          let response = await this.$axios.$put('/api/auth/user', userData);

          if (response.success) {
            this.name = '';
            this.email = '';
            this.password = '';

            await this.$auth.fetchUser();
            this.$router.push('/');
          };
        } catch (err) {
          console.log(err);
        }
      },

      async onLogout() {
        await this.$auth.logout();
      }
    }
}
</script>
