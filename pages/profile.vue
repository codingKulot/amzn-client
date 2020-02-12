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
              <input class="a-input-text" style="width: 100%" v-model="name" :placeholder="$auth.$state.user.name" />
            </div>
            <!-- Email -->
            <div class="a-spacing-top-medium">
              <label>Email</label>
              <input class="a-input-text" style="width: 100%" v-model="email" :placeholder="$auth.$state.user.email" />
            </div>
            <!-- Password -->
            <div class="a-spacing-top-medium">
              <label>Password</label>
              <input type="password" class="a-input-text" style="width: 100%" v-model="password" />
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
export default {
    data() {
        return {
            name: '',
            email: '',
            password: ''
        };
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
