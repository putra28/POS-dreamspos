<template>
  <div class="account-page">
    <div class="account-content">
      <div class="login-wrapper forgot-pass-wrap bg-img">
        <div class="login-content">
          <form @submit.prevent="submitForm">
            <div class="login-userset">
              <div class="login-logo logo-normal">
                <img src="@/assets/img/logo.png" alt="img" />
              </div>
              <router-link to="/dashboard" class="login-logo logo-white">
                <img src="@/assets/img/logo-white.png" alt="" />
              </router-link>
              <div class="login-userheading">
                <h3>Forgot password?</h3>
                <h4>
                  If you forgot your password, well, then we’ll email you instructions to
                  reset your password.
                </h4>
              </div>
              <div class="form-login">
                <label>Email</label>
                <div class="form-addons">
                  <input type="email" class="form-control" />
                  <img src="@/assets/img/icons/mail.svg" alt="img" />
                </div>
              </div>
              <div class="form-login">
                <button type="submit" class="btn btn-login">Sign Up</button>
              </div>
              <div class="signinform text-center">
                <h4>
                  Return to<router-link to="/" class="hover-a"> login </router-link>
                </h4>
              </div>
              <div class="form-setlogin or-text">
                <h4>OR</h4>
              </div>
              <div class="form-sociallink">
                <ul class="d-flex justify-content-center">
                  <li>
                    <a href="javascript:void(0);" class="facebook-logo">
                      <img src="@/assets/img/icons/facebook-logo.svg" alt="Facebook" />
                    </a>
                  </li>
                  <li>
                    <a href="javascript:void(0);">
                      <img src="@/assets/img/icons/google.png" alt="Google" />
                    </a>
                  </li>
                  <li>
                    <a href="javascript:void(0);" class="apple-logo">
                      <img src="@/assets/img/icons/apple-logo.svg" alt="Apple" />
                    </a>
                  </li>
                </ul>
              </div>
              <div
                class="my-4 d-flex justify-content-center align-items-center copyright-text"
              >
                <p>Copyright &copy; {{ new Date().getFullYear() }} DreamsPOS. All rights reserved</p>
              </div>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    submitForm() {
      this.$router.push("/");
    },
  },

}
</script>
